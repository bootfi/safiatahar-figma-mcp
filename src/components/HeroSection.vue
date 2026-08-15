<script setup>
import { computed, ref, onMounted, onUnmounted } from 'vue'
import { getAssetUrl } from '../utils/assets.js'

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
    ? getAssetUrl('/images/hero-mobile-bg-63e0d6.png') 
    : getAssetUrl('/images/hero-desktop-bg.png')
})
</script>

<template>
  <section class="hero-section" id="home">
    <div class="hero-bg" :style="{ backgroundImage: `url(${bgImage})` }"></div>
    
    <div class="hero-container sf-container">
      <div class="hero-content">
        <!-- Logo watermark -->
        <img class="hero-watermark" :src="getAssetUrl('/icons/logo-watermark.svg')" alt="Safia Watermark" />
        
        <div class="hero-quote">
          <h1 class="hero-title">
            <span class="hero-title__part-1">أؤمن أن بداخل كل إنسان قوة..</span>
            <span class="hero-title__part-2">ومهمتي أن أوقظها</span>
          </h1>
        </div>

        <!-- Signature moved to hero-content level for correct absolute positioning -->
        <img class="hero-signature" :src="getAssetUrl('/icons/signature.svg')" alt="Safia Signature" />

        <button class="hero-btn">عش التحول الآن</button>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero-section {
  position: relative;
  width: 100%;
  height: 1024px;
  overflow: hidden;
  background-color: var(--sf-teal-deep);
}

.hero-bg {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-size: cover;
  background-position: center top;
  background-repeat: no-repeat;
  z-index: 1;
}

.hero-container {
  position: relative;
  height: 100%;
  max-width: 1440px;
  margin: 0 auto;
  z-index: 2;
  pointer-events: none;
}

.hero-content {
  position: relative;
  width: 100%;
  height: 100%;
}

.hero-watermark {
  position: absolute;
  left: -20px;
  top: 174px;
  opacity: 0.08;
  width: 577px;
  height: auto;
  pointer-events: none;
}

.hero-quote {
  position: absolute;
  top: 766px;
  right: 80px; /* 1440 - (988 + 372) = 80px */
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  text-align: right;
  width: 372px;
}

.hero-title {
  font-family: var(--sf-font-secondary);
  font-weight: 700;
  font-size: 40px;
  line-height: 1.5;
  color: #F8F5EF;
  margin: 0;
  padding: 0;
  display: block;
}

.hero-title__part-1 {
  display: block;
  color: #F8F5EF;
  width: 372px;
  text-align: right;
}

.hero-title__part-2 {
  display: block;
  width: 271px;
  margin-top: 68px; /* Figma: 834 - 766 = 68px offset from quote top */
  margin-right: 85px; /* (1440-1004-271) - (1440-988-372) = 165 - 80 = 85px offset from parent right */
  text-align: center;
  /* Vertical gold gradient text per Figma */
  background: var(--sf-gradient-gold-vertical);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  color: transparent; /* Fallback */
}

/* Signature positioned absolutely relative to hero-content (Figma: x:1012, y:901) */
.hero-signature {
  position: absolute;
  top: 901px;
  left: 1012px;
  width: 89.77px;
  height: 83px;
}

.hero-btn {
  pointer-events: auto;
  position: absolute;
  top: 798px;
  left: 96px;
  width: 376px;
  height: 48px;
  border-radius: var(--radius-full);         /* 1000px — Radius-full */
  background: var(--sf-gradient-gold-btn);
  color: var(--color-black-500);
  font-family: var(--font-family-primary);     /* Noto Naskh Arabic */
  font-weight: var(--font-weight-bold);        /* 700 */
  font-size: var(--font-size-sm);              /* 16px — Font-size-sm */
  line-height: 1.5em;
  padding: var(--spacing-xs) var(--spacing-sm); /* 8px 16px */
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 4px 15px rgba(184, 151, 95, 0.2);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.hero-btn:hover {
  transform: translateY(-2px);
  box-shadow: 0 6px 20px rgba(184, 151, 95, 0.4);
}

@media (max-width: 1024px) {
  .hero-quote {
    right: 5%;
  }
  .hero-btn {
    left: 5%;
  }
}

@media (max-width: 768px) {
  .hero-section {
    height: 850px;
  }
  .hero-bg {
    background-size: 100% 100%; /* Figma: scaleMode STRETCH */
  }
  .hero-content {
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    align-items: center;
    padding-bottom: 72px;
  }
  .hero-quote {
    position: relative;
    top: auto;
    right: auto;
    align-items: center;
    text-align: center;
    margin-bottom: 32px;
  }
  .hero-title {
    font-size: 32px;
    align-items: center;
    text-align: center;
  }
  .hero-title__part-1 {
    width: auto;
    text-align: center;
  }
  .hero-title__part-2 {
    width: auto;
    margin-top: 16px;
    margin-right: 0;
    text-align: center;
  }
  .hero-signature {
    position: relative;
    top: auto;
    left: auto;
    width: 60px;
    height: auto;
    align-self: center;
    margin-top: 8px;
    margin-bottom: 16px;
  }
  .hero-btn {
    position: relative;
    bottom: auto;
    left: auto;
    top: auto;
    width: 262px;
    height: var(--spacing-xl);                    /* 48px — Spacing-xl */
    padding: 12px var(--spacing-lg);              /* 12px 32px (12 has no token) */
    font-size: var(--font-size-sm);               /* 16px — Font-size-sm */
    font-family: var(--font-family-primary);
  }
  .hero-watermark {
    width: 336px;
    left: 28.5px; /* Figma x: 28.5 */
    top: 50px;    /* Figma y: 50 */
    transform: none;
  }
}
</style>
