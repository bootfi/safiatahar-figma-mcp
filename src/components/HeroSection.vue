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
    ? '/images/hero-mobile-bg-63e0d6.png' 
    : '/images/hero-desktop-bg.png'
})
</script>

<template>
  <section class="hero-section" id="home">
    <div class="hero-bg" :style="{ backgroundImage: `url(${bgImage})` }"></div>
    
    <div class="hero-container sf-container">
      <div class="hero-content">
        <!-- Logo watermark -->
        <img class="hero-watermark" src="/icons/logo-watermark.svg" alt="Safia Watermark" />
        
        <div class="hero-quote">
          <h1 class="hero-title">
            <span class="hero-title__part-1">أؤمن أن بداخل كل إنسان قوة..</span>
            <span class="hero-title__part-2">ومهمتي أن أوقظها</span>
          </h1>
          <img class="hero-signature" src="/icons/signature.svg" alt="Safia Signature" />
        </div>

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
  line-height: 1.5; /* Figma line height normal */
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
  color: var(--sf-gold);
  width: 271px;
  margin-top: 20px; /* roughly 834 - 766 - some font offset */
  margin-right: 85px; /* (1440-1275) - 80 = 85px offset from parent right */
  text-align: center;
}

.hero-signature {
  position: absolute;
  top: 901px;
  right: 338px; /* 1440 - (1012 + 90) = 338px */
  width: 90px;
  height: auto;
}

.hero-btn {
  pointer-events: auto;
  position: absolute;
  top: 798px;
  left: 96px;
  width: 376px;
  height: 48px;
  border-radius: 1000px;
  background: var(--sf-gradient-gold);
  color: var(--sf-dark);
  font-family: var(--sf-font-body);
  font-weight: 700;
  font-size: 18px;
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
  .hero-signature {
    margin-right: 0;
    align-self: center;
  }
  .hero-btn {
    position: relative;
    bottom: auto;
    left: auto;
    width: 262px;
    height: 48px;
    padding: 12px 32px;
    font-size: 16px;
  }
  .hero-watermark {
    width: 336px;
    left: 50%;
    transform: translateX(-50%);
    top: 20%;
  }
}
</style>
