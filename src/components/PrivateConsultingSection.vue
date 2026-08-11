<script setup>
import { computed, ref, onMounted, onUnmounted } from 'vue'

const isMobile = ref(false)

const handleResize = () => {
  isMobile.value = window.innerWidth <= 768
}

onMounted(() => {
  handleResize()
  window.addEventListener('resize', handleResize)
})

onUnmounted(() => {
  window.removeEventListener('resize', handleResize)
})

const bgImage = computed(() => {
  return isMobile.value 
    ? '/images/consulting-mobile-bg.png' 
    : '/images/consulting-bg.png'
})
</script>

<template>
  <section class="consulting-section" id="consulting">
    <div class="consulting-bg" :style="{ backgroundImage: `url(${bgImage})` }"></div>
    <div class="consulting-overlay"></div>
    
    <div class="consulting-container sf-container">
      <div class="consulting-content">
        <div class="consulting-header">
          <h2 class="consulting-title">استشارات خاصة</h2>
          <h3 class="consulting-subtitle">عمل مباشر مع صفية، حضوريًا أو عن بعد</h3>
        </div>
        
        <p class="consulting-desc">
          مساحة خاصة واهتمام كامل، ومسار مصمّم بعناية لتسريع التحوّل خطوة بخطوة.
        </p>

        <button class="consulting-btn">احجز استشارتك</button>
      </div>
    </div>
  </section>
</template>

<style scoped>
.consulting-section {
  position: relative;
  width: 100%;
  min-height: 650px; /* From desktop bg image */
  display: flex;
  align-items: center;
}

.consulting-bg {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  z-index: 1;
}

.consulting-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  /* RTL: gradient fades from right to left */
  background: linear-gradient(270deg, rgba(0,0,0,0.7) 0%, rgba(0,0,0,0) 100%);
  z-index: 2;
}

.consulting-container {
  position: relative;
  z-index: 3;
  width: 100%;
  display: flex;
  padding: 24px 80px; /* Figma: 24px 80px */
}

.consulting-content {
  max-width: 600px;
  display: flex;
  flex-direction: column;
  gap: 32px;
}

.consulting-header {
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.consulting-title {
  font-family: var(--sf-font-secondary);
  font-weight: 700;
  font-size: 48px;
  color: #FFFFFF;
}

.consulting-subtitle {
  font-family: var(--sf-font-body);
  font-weight: 500;
  font-size: 24px;
  color: var(--sf-gold);
}

.consulting-desc {
  font-family: var(--sf-font-body);
  font-weight: 500;
  font-size: 32px; /* Figma: 32px */
  line-height: 1.5;
  color: var(--sf-teal-deep); /* Figma: #093B33 */
}

.consulting-btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 8px 16px;
  border-radius: 1000px;
  background: var(--sf-gradient-teal-btn); /* Figma: teal gradient */
  color: #fff;
  font-family: var(--sf-font-secondary);
  font-weight: 700;
  font-size: 16px;
  line-height: 1.5em;
  width: 100%; /* Figma: alignSelf stretch */
  height: 48px;
  transition: all 0.3s ease;
}

@media (max-width: 768px) {
  .consulting-section {
    min-height: 931px; /* Mobile bg height */
    align-items: flex-end;
  }
  .consulting-overlay {
    background: linear-gradient(180deg, rgba(0,0,0,0) 0%, rgba(0,0,0,0.8) 100%);
  }
  .consulting-container {
    padding: 48px 24px;
  }
  .consulting-content {
    gap: 24px;
    text-align: center;
    align-items: center;
  }
  .consulting-title {
    font-size: 32px;
  }
  .consulting-subtitle {
    font-size: 16px;
  }
  .consulting-desc {
    font-size: 16px;
  }
  .consulting-btn {
    width: 100%;
  }
}
</style>
