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
  padding: var(--spacing-md) var(--spacing-3xl); /* 24px 80px */
}

.consulting-content {
  max-width: 600px;
  display: flex;
  flex-direction: column;
  gap: var(--spacing-lg);                /* 32px — Spacing-lg */
}

.consulting-header {
  display: flex;
  flex-direction: column;
  gap: var(--spacing-xs);                /* 8px — Spacing-xs */
}

.consulting-title {
  font-family: var(--font-family-primary);  /* Noto Naskh Arabic */
  font-weight: var(--font-weight-bold);
  font-size: var(--font-size-xl);           /* 48px — Font-size-xl */
  color: #ffffff;
}

.consulting-subtitle {
  font-family: var(--font-family-secondary); /* Tajawal */
  font-weight: var(--font-weight-medium);
  font-size: var(--font-size-base);          /* 24px — Font-size-base */
  color: var(--color-accent-500);
}

.consulting-desc {
  font-family: var(--font-family-secondary);
  font-weight: var(--font-weight-medium);
  font-size: var(--font-size-lg);            /* 32px — Font-size-lg */
  line-height: 1.5;
  color: var(--color-primary-500);
}

.consulting-btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: var(--spacing-xs) var(--spacing-sm); /* 8px 16px */
  border-radius: var(--radius-full);            /* 1000px — Radius-full */
  background: var(--sf-gradient-teal-btn);
  color: #fff;
  font-family: var(--font-family-primary);
  font-weight: var(--font-weight-bold);
  font-size: var(--font-size-sm);               /* 16px — Font-size-sm */
  line-height: 1.5em;
  width: 100%;
  height: var(--spacing-xl);                    /* 48px — Spacing-xl */
  transition: all 0.3s ease;
}

@media (max-width: 768px) {
  .consulting-section {
    min-height: 931px;
    align-items: flex-end;
  }
  .consulting-overlay {
    background: linear-gradient(180deg, rgba(0,0,0,0) 0%, rgba(0,0,0,0.8) 100%);
  }
  .consulting-container {
    padding: var(--spacing-xl) var(--spacing-md); /* 48px 24px */
  }
  .consulting-content {
    gap: var(--spacing-md);                       /* 24px */
    text-align: center;
    align-items: center;
  }
  .consulting-title {
    font-size: var(--font-size-lg);               /* 32px */
  }
  .consulting-subtitle {
    font-size: var(--font-size-sm);               /* 16px */
  }
  .consulting-desc {
    font-size: var(--font-size-sm);               /* 16px */
  }
  .consulting-btn {
    width: 100%;
  }
}
</style>
