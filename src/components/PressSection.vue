<script setup>
import { getAssetUrl } from '../utils/assets.js'

// Press logos from Figma
const logos = [
  getAssetUrl('/images/press-logo-1-2b78f1.png'),
  getAssetUrl('/images/press-logo-2-753ec8.png'),
  getAssetUrl('/images/press-logo-3-1b1243.png'),
  getAssetUrl('/images/press-logo-4-44141c.png'),
  getAssetUrl('/images/press-logo-5.png')
]

// Duplicate for marquee effect
const marqueeLogos = [...logos, ...logos, ...logos]
</script>

<template>
  <section class="press-section">
    <h3 class="press-title">تم الظهور في</h3>
    
    <div class="press-marquee-wrapper">
      <div class="press-marquee">
        <div 
          v-for="(logo, index) in marqueeLogos" 
          :key="index"
          class="press-logo-box"
        >
          <img :src="logo" alt="Press Logo" />
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.press-section {
  padding: var(--spacing-md);              /* 24px — Spacing-md */
  background: var(--sf-gradient-teal);
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: var(--spacing-md);                  /* 24px — Spacing-md */
  overflow: hidden;
}

.press-title {
  font-family: var(--font-family-secondary); /* Tajawal */
  font-weight: var(--font-weight-medium);
  font-size: var(--font-size-base);          /* 24px — Font-size-base */
  color: var(--color-surface-main);
}

.press-marquee-wrapper {
  width: 100%;
  max-width: 1440px;
  overflow: hidden;
  position: relative;
}

.press-marquee {
  display: flex;
  align-items: center;
  gap: var(--spacing-2xl);                 /* 64px — Spacing-2xl */
  width: max-content;
  animation: scroll 30s linear infinite;
}

.press-logo-box {
  height: 60px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.press-logo-box img {
  max-height: 100%;
  max-width: 200px;
  object-fit: contain;
  filter: brightness(0) invert(1); /* Ensure logos are white if they are black initially */
}

@keyframes scroll {
  0% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(calc(100% / 3)); /* Adjust based on duplication count, assuming RTL scrolling (to right) */
  }
}

@media (max-width: 768px) {
  .press-section {
    padding: var(--spacing-md) 0;
    gap: var(--spacing-md);
  }
  .press-title {
    font-size: var(--font-size-body);      /* 20px */
  }
  .press-logo-box {
    height: 40px;
  }
}
</style>
