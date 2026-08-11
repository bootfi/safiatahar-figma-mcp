<script setup>
// Press logos from Figma
const logos = [
  '/images/press-logo-1-2b78f1.png',
  '/images/press-logo-2-753ec8.png',
  '/images/press-logo-3-1b1243.png',
  '/images/press-logo-4-44141c.png',
  '/images/press-logo-5.png'
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
  padding: 24px;
  background: var(--sf-gradient-teal);
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 24px;
  overflow: hidden;
}

.press-title {
  font-family: var(--sf-font-body);
  font-weight: 500;
  font-size: 24px;
  color: var(--sf-bg-primary); /* FCFBF8 */
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
  gap: 64px;
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
    padding: 24px 0;
    gap: 24px;
  }
  .press-title {
    font-size: 20px;
  }
  .press-logo-box {
    height: 40px;
  }
}
</style>
