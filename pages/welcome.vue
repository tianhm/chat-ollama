<script setup>
const { t } = useI18n()
const router = useRouter()

const goToSettings = () => {
  router.push('/settings')
}
</script>
<template>
  <div class="welcome-shell relative min-h-full overflow-hidden">
    <div class="welcome-glow" aria-hidden="true">
      <span class="welcome-glow-shape glow-1"></span>
      <span class="welcome-glow-shape glow-2"></span>
      <span class="welcome-glow-shape glow-3"></span>
    </div>

    <div class="relative mx-auto flex w-full max-w-6xl flex-col gap-12 px-6 py-12 sm:py-16 lg:py-20">
      <section class="grid items-center gap-10 lg:grid-cols-[1.1fr,0.9fr]">
        <div class="welcome-reveal space-y-6">
          <div class="welcome-pill">
            <span class="welcome-dot"></span>
            {{ t("home.quickStart") }}
          </div>
          <h1 class="welcome-heading text-4xl font-semibold leading-tight text-slate-900 sm:text-5xl lg:text-6xl dark:text-slate-50">
            {{ t("home.welcome") }}
          </h1>
          <p class="welcome-subtitle text-base sm:text-lg max-w-xl">
            {{ t("home.subtitle") }}
          </p>
          <p class="welcome-description text-sm max-w-xl leading-relaxed">
            {{ t("home.description") }}
          </p>
          <div class="flex flex-col gap-4 sm:flex-row sm:items-center">
            <button
              @click="goToSettings"
              class="welcome-button"
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
            <span class="welcome-chip">
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
            <span class="welcome-index">01</span>
          </div>
          <p class="mt-4 text-base font-semibold text-slate-900 dark:text-white">
            {{ t("home.feature1") }}
          </p>
          <div class="welcome-bar welcome-bar-orange"></div>
        </div>
        <div class="welcome-card welcome-reveal welcome-delay-3 lg:col-span-4">
          <div class="flex items-center gap-3 text-sky-500">
            <svg viewBox="0 0 24 24" class="h-5 w-5" fill="none" stroke="currentColor" stroke-width="1.8" aria-hidden="true">
              <path stroke-linecap="round" stroke-linejoin="round" d="M12 5v6l4 2M21 12a9 9 0 11-18 0 9 9 0 0118 0z" />
            </svg>
            <span class="welcome-index">02</span>
          </div>
          <p class="mt-4 text-base font-semibold text-slate-900 dark:text-white">
            {{ t("home.feature2") }}
          </p>
          <div class="welcome-bar welcome-bar-sky"></div>
        </div>
        <div class="welcome-card welcome-reveal welcome-delay-4 lg:col-span-3">
          <div class="flex items-center gap-3 text-emerald-500">
            <svg viewBox="0 0 24 24" class="h-5 w-5" fill="none" stroke="currentColor" stroke-width="1.8" aria-hidden="true">
              <path stroke-linecap="round" stroke-linejoin="round" d="M12 4.5l6 3.5v5.5c0 3.8-2.6 6.7-6 7.5-3.4-.8-6-3.7-6-7.5V8l6-3.5z" />
            </svg>
            <span class="welcome-index">03</span>
          </div>
          <p class="mt-4 text-base font-semibold text-slate-900 dark:text-white">
            {{ t("home.feature3") }}
          </p>
          <div class="welcome-bar welcome-bar-emerald"></div>
        </div>
      </section>

    </div>
  </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Manrope:wght@400;500;600;700&family=Sora:wght@400;500;600;700&display=swap');

.welcome-shell {
  --bg: #eef2f6;
  --surface: #f7f9fc;
  --text: #0f172a;
  --muted: #64748b;
  --shadow-dark: rgba(148, 163, 184, 0.45);
  --shadow-light: rgba(255, 255, 255, 0.9);
  --accent: #0ea5e9;
  --accent-strong: #0284c7;
  background: linear-gradient(145deg, #eef2f6, #e6edf7);
  color: var(--text);
  font-family: "Manrope", "SF Pro Text", "SF Pro Icons", "Helvetica Neue", sans-serif;
}

.welcome-heading {
  font-family: "Sora", "SF Pro Text", "SF Pro Icons", "Helvetica Neue", sans-serif;
  letter-spacing: -0.03em;
}

:global(.dark) .welcome-shell {
  --bg: #0f172a;
  --surface: #111c2e;
  --text: #e2e8f0;
  --muted: #94a3b8;
  --shadow-dark: rgba(2, 6, 23, 0.9);
  --shadow-light: rgba(148, 163, 184, 0.12);
  --accent: #38bdf8;
  --accent-strong: #0ea5e9;
  background: linear-gradient(145deg, #0b1220, #111827);
}

.welcome-glow {
  position: absolute;
  inset: -10%;
  pointer-events: none;
}

.welcome-glow-shape {
  position: absolute;
  border-radius: 999px;
  filter: blur(70px);
  opacity: 0.35;
  transform: translateZ(0);
}

.glow-1 {
  width: 38vw;
  height: 38vw;
  top: -8%;
  left: -6%;
  background: radial-gradient(circle at 30% 30%, rgba(56, 189, 248, 0.25), rgba(56, 189, 248, 0));
}

.glow-2 {
  width: 34vw;
  height: 34vw;
  top: 2%;
  right: -8%;
  background: radial-gradient(circle at 30% 30%, rgba(14, 165, 233, 0.2), rgba(14, 165, 233, 0));
}

.glow-3 {
  width: 46vw;
  height: 46vw;
  bottom: -18%;
  left: 18%;
  background: radial-gradient(circle at 30% 30%, rgba(16, 185, 129, 0.18), rgba(16, 185, 129, 0));
}

.welcome-pill {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  border-radius: 999px;
  padding: 0.3rem 1rem;
  font-size: 0.7rem;
  font-weight: 600;
  letter-spacing: 0.12em;
  color: var(--muted);
  background: var(--surface);
  box-shadow: inset 4px 4px 8px var(--shadow-dark), inset -4px -4px 8px var(--shadow-light);
}

.welcome-subtitle {
  color: var(--text);
  opacity: 0.78;
}

.welcome-description {
  color: var(--muted);
}

.welcome-dot {
  width: 0.45rem;
  height: 0.45rem;
  border-radius: 999px;
  background: radial-gradient(circle at 30% 30%, #38bdf8, #0ea5e9);
  box-shadow: 2px 2px 4px var(--shadow-dark), -2px -2px 4px var(--shadow-light);
}

.welcome-card {
  border-radius: 1.5rem;
  background: var(--surface);
  padding: 1.5rem;
  box-shadow: 18px 18px 36px var(--shadow-dark), -18px -18px 36px var(--shadow-light);
  transition: box-shadow 200ms ease;
}

.welcome-card:hover {
  box-shadow: 22px 22px 44px var(--shadow-dark), -22px -22px 44px var(--shadow-light);
}

.welcome-button {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  border-radius: 999px;
  padding: 0.85rem 1.6rem;
  font-size: 0.9rem;
  font-weight: 600;
  color: #fff;
  background: linear-gradient(135deg, var(--accent), var(--accent-strong));
  box-shadow: 12px 12px 24px var(--shadow-dark), -10px -10px 20px var(--shadow-light);
  transition: box-shadow 200ms ease, filter 200ms ease;
  cursor: pointer;
}

.welcome-button:hover {
  box-shadow: 16px 16px 30px var(--shadow-dark), -12px -12px 24px var(--shadow-light);
  filter: brightness(1.02);
}

.welcome-button:focus-visible {
  outline: 2px solid var(--accent);
  outline-offset: 4px;
}

.welcome-chip {
  border-radius: 999px;
  padding: 0.2rem 0.7rem;
  font-size: 0.75rem;
  font-weight: 600;
  color: var(--muted);
  background: var(--surface);
  box-shadow: inset 4px 4px 8px var(--shadow-dark), inset -4px -4px 8px var(--shadow-light);
}

.welcome-step {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  border-radius: 1rem;
  background: var(--surface);
  padding: 0.75rem 1rem;
  box-shadow: inset 8px 8px 16px var(--shadow-dark), inset -8px -8px 16px var(--shadow-light);
}

.welcome-step-number {
  display: grid;
  place-items: center;
  width: 2rem;
  height: 2rem;
  border-radius: 999px;
  background: var(--surface);
  color: var(--accent-strong);
  font-size: 0.85rem;
  font-weight: 600;
  box-shadow: 4px 4px 8px var(--shadow-dark), -4px -4px 8px var(--shadow-light);
}

.welcome-index {
  font-size: 0.7rem;
  font-weight: 600;
  letter-spacing: 0.28em;
  text-transform: uppercase;
  color: var(--muted);
}

.welcome-bar {
  margin-top: 1.5rem;
  height: 0.3rem;
  width: 3.5rem;
  border-radius: 999px;
  box-shadow: inset 2px 2px 4px var(--shadow-dark), inset -2px -2px 4px var(--shadow-light);
}

.welcome-bar-orange {
  background: linear-gradient(135deg, #fdba74, #fb923c);
}

.welcome-bar-sky {
  background: linear-gradient(135deg, #7dd3fc, #38bdf8);
}

.welcome-bar-emerald {
  background: linear-gradient(135deg, #6ee7b7, #34d399);
}

.welcome-shell :deep(a) {
  color: var(--accent-strong);
  font-weight: 600;
}

.welcome-shell :deep(a:hover) {
  color: var(--accent);
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
</style>
