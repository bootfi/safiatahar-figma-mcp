<script setup>
import { getAssetUrl } from '../utils/assets.js'
</script>

<template>
  <section class="cta-banner-section">
    <div class="cta-bg" :style="{ backgroundImage: `url(${getAssetUrl('/images/cta-banner-bg.png')})` }"></div>
    <div class="cta-overlay"></div>
    
    <div class="cta-container sf-container">
      <div class="cta-content">
        <h2 class="cta-title">رحلتك تبدأ بقرارٍ واحد</h2>
        <button class="cta-btn">ابدأ الآن</button>
      </div>
    </div>
  </section>
</template>

<style scoped>
.cta-banner-section {
  position: relative;
  width: 100%;
  height: 400px; /* Figma: 400px */
  display: flex;
  align-items: center;
  justify-content: center;
}

.cta-bg {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: url('/images/cta-banner-bg.png');
  background-size: 100% 100%; /* Figma: STRETCH with crop */
  background-position: center;
  background-repeat: no-repeat;
  z-index: 1;
}

.cta-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.2); /* Figma: rgba(0,0,0,0.2) */
  z-index: 2;
}

.cta-container {
  position: relative;
  z-index: 3;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: var(--spacing-md) var(--spacing-3xl); /* 24px 80px */
}

.cta-content {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: var(--spacing-lg);               /* 32px — Spacing-lg */
  text-align: center;
  width: 496px;
}

.cta-title {
  font-family: var(--font-family-primary);  /* Noto Naskh Arabic */
  font-weight: var(--font-weight-bold);
  font-size: var(--font-size-2xl);          /* 64px — Font-size-2xl */
  color: var(--color-white-400);
}

.cta-btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: var(--spacing-xs) var(--spacing-sm); /* 8px 16px */
  border-radius: var(--radius-full);            /* 1000px — Radius-full */
  background: var(--sf-gradient-gold-btn);
  color: var(--color-black-500);
  font-family: var(--font-family-primary);
  font-weight: var(--font-weight-bold);
  font-size: var(--font-size-sm);               /* 16px — Font-size-sm */
  line-height: 1.5em;
  width: 496px;
  height: var(--spacing-xl);                    /* 48px — Spacing-xl */
  transition: opacity 0.3s ease;
}

.cta-btn:hover {
  opacity: 0.9;
}

@media (max-width: 768px) {
  .cta-banner-section {
    height: 400px;
    padding: var(--spacing-md);           /* 24px */
  }
  .cta-container {
    padding: var(--spacing-md);           /* 24px */
  }
  .cta-content {
    width: 100%;
    gap: var(--spacing-lg);               /* 32px */
  }
  .cta-title {
    font-size: var(--font-size-lg);       /* 32px */
  }
  .cta-btn {
    width: 100%;
  }
}
</style>
