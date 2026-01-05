<script setup>
const { t } = useI18n()
const router = useRouter()

const goToSettings = () => {
  router.push('/settings')
}
</script>
<template>
  <div class="welcome-shell relative min-h-full overflow-hidden bg-slate-50 dark:bg-slate-950">
    <div class="welcome-aurora" aria-hidden="true">
      <span class="aurora-blob aurora-1"></span>
      <span class="aurora-blob aurora-2"></span>
      <span class="aurora-blob aurora-3"></span>
    </div>

    <div class="relative mx-auto flex w-full max-w-6xl flex-col gap-12 px-6 py-12 sm:py-16 lg:py-20">
      <section class="grid items-center gap-10 lg:grid-cols-[1.1fr,0.9fr]">
        <div class="welcome-reveal space-y-6">
          <div class="inline-flex items-center gap-3 rounded-full border border-slate-200/70 bg-white/70 px-4 py-1 text-[0.65rem] font-semibold uppercase tracking-[0.3em] text-slate-600 shadow-sm backdrop-blur dark:border-slate-700/60 dark:bg-slate-900/60 dark:text-slate-300">
            <span class="welcome-dot"></span>
            {{ t("home.quickStart") }}
          </div>
          <h1 class="welcome-heading text-4xl font-semibold leading-tight text-slate-900 sm:text-5xl lg:text-6xl dark:text-slate-50">
            {{ t("home.welcome") }}
          </h1>
          <p class="text-base text-slate-600 sm:text-lg dark:text-slate-300 max-w-xl">
            {{ t("home.subtitle") }}
          </p>
          <p class="text-sm text-slate-500 dark:text-slate-400 max-w-xl leading-relaxed">
            {{ t("home.description") }}
          </p>
          <div class="flex flex-col gap-4 sm:flex-row sm:items-center">
            <button
              @click="goToSettings"
              class="inline-flex items-center justify-center rounded-full bg-orange-500 px-6 py-3 text-sm font-semibold text-white shadow-lg shadow-orange-500/20 transition-colors hover:bg-orange-400 focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-orange-400 focus-visible:ring-offset-2 focus-visible:ring-offset-slate-50 dark:focus-visible:ring-offset-slate-950"
            >
              {{ t("home.getStarted") }}
            </button>
          </div>
        </div>

        <div class="welcome-card welcome-reveal welcome-delay-1">
          <div class="flex items-center justify-between">
            <h2 class="welcome-heading text-lg font-semibold text-slate-900 dark:text-white">
              {{ t("home.quickStart") }}
            </h2>
            <span class="rounded-full border border-slate-200/70 bg-white/70 px-3 py-1 text-xs font-semibold text-slate-500 dark:border-slate-700/60 dark:bg-slate-900/60 dark:text-slate-300">
              01-02
            </span>
          </div>
          <div class="mt-6 grid gap-3">
            <div class="welcome-step">
              <div class="welcome-step-number">1</div>
              <div v-html="t('home.step1')" class="text-sm text-slate-700 dark:text-slate-200"></div>
            </div>
            <div class="welcome-step">
              <div class="welcome-step-number">2</div>
              <div v-html="t('home.step2')" class="text-sm text-slate-700 dark:text-slate-200"></div>
            </div>
          </div>
        </div>
      </section>

      <section class="grid gap-4 lg:grid-cols-12">
        <div class="welcome-card welcome-reveal welcome-delay-2 lg:col-span-5">
          <div class="flex items-center gap-3 text-orange-500">
            <svg viewBox="0 0 24 24" class="h-5 w-5" fill="none" stroke="currentColor" stroke-width="1.8" aria-hidden="true">
              <path stroke-linecap="round" stroke-linejoin="round" d="M12 3l2.5 5 5.5.7-4 3.9.9 5.6L12 15.7 7.1 18.2 8 12.6 4 8.7 9.5 8z" />
            </svg>
            <span class="text-xs font-semibold uppercase tracking-[0.25em] text-slate-400 dark:text-slate-500">01</span>
          </div>
          <p class="mt-4 text-base font-semibold text-slate-900 dark:text-white">
            {{ t("home.feature1") }}
          </p>
          <div class="mt-6 h-1 w-16 rounded-full bg-gradient-to-r from-orange-400 via-orange-300 to-orange-200"></div>
        </div>
        <div class="welcome-card welcome-reveal welcome-delay-3 lg:col-span-4">
          <div class="flex items-center gap-3 text-sky-500">
            <svg viewBox="0 0 24 24" class="h-5 w-5" fill="none" stroke="currentColor" stroke-width="1.8" aria-hidden="true">
              <path stroke-linecap="round" stroke-linejoin="round" d="M12 5v6l4 2M21 12a9 9 0 11-18 0 9 9 0 0118 0z" />
            </svg>
            <span class="text-xs font-semibold uppercase tracking-[0.25em] text-slate-400 dark:text-slate-500">02</span>
          </div>
          <p class="mt-4 text-base font-semibold text-slate-900 dark:text-white">
            {{ t("home.feature2") }}
          </p>
          <div class="mt-6 h-1 w-16 rounded-full bg-gradient-to-r from-sky-400 via-sky-300 to-sky-200"></div>
        </div>
        <div class="welcome-card welcome-reveal welcome-delay-4 lg:col-span-3">
          <div class="flex items-center gap-3 text-emerald-500">
            <svg viewBox="0 0 24 24" class="h-5 w-5" fill="none" stroke="currentColor" stroke-width="1.8" aria-hidden="true">
              <path stroke-linecap="round" stroke-linejoin="round" d="M12 4.5l6 3.5v5.5c0 3.8-2.6 6.7-6 7.5-3.4-.8-6-3.7-6-7.5V8l6-3.5z" />
            </svg>
            <span class="text-xs font-semibold uppercase tracking-[0.25em] text-slate-400 dark:text-slate-500">03</span>
          </div>
          <p class="mt-4 text-base font-semibold text-slate-900 dark:text-white">
            {{ t("home.feature3") }}
          </p>
          <div class="mt-6 h-1 w-16 rounded-full bg-gradient-to-r from-emerald-400 via-emerald-300 to-emerald-200"></div>
        </div>
      </section>

    </div>
  </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;700&family=Space+Grotesk:wght@400;500;600;700&display=swap');

.welcome-shell {
  font-family: "DM Sans", "SF Pro Text", "SF Pro Icons", "Helvetica Neue", sans-serif;
}

.welcome-heading {
  font-family: "Space Grotesk", "SF Pro Text", "SF Pro Icons", "Helvetica Neue", sans-serif;
  letter-spacing: -0.02em;
}

.welcome-aurora {
  position: absolute;
  inset: -20%;
  pointer-events: none;
}

.aurora-blob {
  position: absolute;
  border-radius: 999px;
  filter: blur(60px);
  opacity: 0.6;
  transform: translateZ(0);
}

.aurora-1 {
  width: 42vw;
  height: 42vw;
  top: -10%;
  left: -5%;
  background: radial-gradient(circle at 30% 30%, rgba(56, 189, 248, 0.75), rgba(59, 130, 246, 0));
}

.aurora-2 {
  width: 36vw;
  height: 36vw;
  top: 5%;
  right: -10%;
  background: radial-gradient(circle at 30% 30%, rgba(251, 146, 60, 0.65), rgba(251, 191, 36, 0));
}

.aurora-3 {
  width: 44vw;
  height: 44vw;
  bottom: -20%;
  left: 20%;
  background: radial-gradient(circle at 30% 30%, rgba(16, 185, 129, 0.5), rgba(14, 116, 144, 0));
}

.welcome-dot {
  width: 0.45rem;
  height: 0.45rem;
  border-radius: 999px;
  background: linear-gradient(135deg, #f97316, #38bdf8);
  box-shadow: 0 0 0 3px rgba(248, 250, 252, 0.7);
}

.welcome-card {
  border-radius: 1.25rem;
  border: 1px solid rgba(148, 163, 184, 0.4);
  background: rgba(255, 255, 255, 0.85);
  padding: 1.5rem;
  box-shadow: 0 20px 50px -40px rgba(15, 23, 42, 0.5);
  backdrop-filter: blur(16px);
}

.welcome-step {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  border-radius: 1rem;
  border: 1px solid rgba(148, 163, 184, 0.35);
  background: rgba(248, 250, 252, 0.9);
  padding: 0.75rem 1rem;
}

.welcome-step-number {
  display: grid;
  place-items: center;
  width: 2rem;
  height: 2rem;
  border-radius: 999px;
  background: linear-gradient(135deg, #0f172a, #1e293b);
  color: #fff;
  font-size: 0.85rem;
  font-weight: 600;
}

.welcome-reveal {
  animation: welcome-reveal 650ms ease both;
}

.welcome-delay-1 {
  animation-delay: 120ms;
}

.welcome-delay-2 {
  animation-delay: 200ms;
}

.welcome-delay-3 {
  animation-delay: 260ms;
}

.welcome-delay-4 {
  animation-delay: 320ms;
}

@keyframes welcome-reveal {
  from {
    opacity: 0;
    transform: translateY(14px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@media (prefers-reduced-motion: reduce) {
  .welcome-reveal {
    animation: none;
  }
}

:global(.dark) .welcome-dot {
  box-shadow: 0 0 0 3px rgba(15, 23, 42, 0.9);
}

:global(.dark) .welcome-card {
  border-color: rgba(148, 163, 184, 0.2);
  background: rgba(15, 23, 42, 0.72);
  box-shadow: 0 24px 60px -48px rgba(0, 0, 0, 0.8);
}

:global(.dark) .welcome-step {
  border-color: rgba(148, 163, 184, 0.2);
  background: rgba(15, 23, 42, 0.7);
}

:global(.dark) .welcome-step-number {
  background: linear-gradient(135deg, #e2e8f0, #94a3b8);
  color: #0f172a;
}
</style>
