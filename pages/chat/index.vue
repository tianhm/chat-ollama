<script setup lang="ts">
import type { ComponentInstance } from 'vue'
import ChatSessionList from '~/components/ChatSessionList.vue'
import Chat from '~/components/Chat.vue'
import type { ChatMessage } from '@/types/chat'

export interface ChatSessionSettings extends Partial<Omit<ChatSession, 'id' | 'createTime'>> { }

const { t } = useI18n()
const chatSessionListRef = shallowRef<ComponentInstance<typeof ChatSessionList>>()
const chatRef = shallowRef<ComponentInstance<typeof Chat>>()
const slideover = useSlideover()
const { isMobile } = useMediaBreakpoints()

const sessionId = ref(0)
const latestMessageId = ref(0)
const isSessionListVisible = ref(true)

watch(isMobile, val => {
  if (!val) {
    slideover.close()
  }
})

function onChangeSettings(data: ChatSessionSettings) {
  chatSessionListRef.value?.updateSessionInfo({ ...data, forceUpdateTitle: true })
}

function onMessage(data: ChatMessage | null) {
  // remove a message if it's null
  if (data === null) {
    return
  }

  chatSessionListRef.value?.updateSessionInfo({
    title: data.content.slice(0, 20),
    updateTime: data.endTime || data.startTime,
  })
  if (latestMessageId.value !== data.id) {
    latestMessageId.value = data.id!
  }
}

function onNewChat() {
  chatSessionListRef.value?.createChat()
}

async function onChangeChatSession(id: number) {
  sessionId.value = id
}

function onOpenSideMenu() {
  slideover.open(ChatSessionList, {
    ref: chatSessionListRef,
    onSelect: onChangeChatSession,
    onClosePanel: () => {
      slideover.close()
    },
    side: 'left',
    preventClose: true,
  })
}

function toggleSidebar() {
  isSessionListVisible.value = !isSessionListVisible.value
}

provide('isSessionListVisible', isSessionListVisible)
</script>

<template>
  <div class="h-full max-w-6xl mx-auto flex flex-1 border border-gray-200 dark:border-gray-800 rounded-md shadow-md"
       style="--chat-side-width:240px">
    <ClientOnly>
      <ChatSessionList ref="chatSessionListRef"
                       class="shrink-0 w-[var(--chat-side-width)] hidden md:block transition-all duration-300"
                       :class="{ 'md:!hidden': !isSessionListVisible }"
                       @select="onChangeChatSession" />
    </ClientOnly>
    <Chat ref="chatRef" v-if="sessionId > 0"
          class="flex-1 md:px-4 pb-4 box-border w-full transition-all duration-300"
          :class="{ 'md:w-full': !isSessionListVisible, 'md:w-[calc(100%-var(--chat-side-width))]': isSessionListVisible }"
          :session-id="sessionId"
          @change-settings="onChangeSettings"
          @message="onMessage"
          @toggle-sidebar="toggleSidebar">
      <template #left-menu-btn>
        <UButton :icon="isSessionListVisible ? 'i-material-symbols-lists-rounded' : 'i-heroicons-chevron-double-right'" color="gray" class="mr-4 md:hidden" :class="{ 'rotate-180': isSessionListVisible }" @click="onOpenSideMenu"></UButton>
      </template>
    </Chat>
    <div v-else class="grow h-full flex justify-center items-center">
      <UButton icon="i-material-symbols-add" color="primary" square @click="onNewChat">{{ t("chat.newChat") }}</UButton>
    </div>
  </div>
</template>
