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
    ? '/images/events-mobile-bg.png' 
    : '/images/events-bg.png'
})
</script>

<template>
  <section class="events-section" id="events">
    <div class="events-bg" :style="{ backgroundImage: `url(${bgImage})` }"></div>
    <div class="events-overlay"></div>
    
    <div class="events-container sf-container">
      <div class="events-content">
        <div class="events-header">
          <h2 class="events-title">الفعاليات الحضورية لعام 2026</h2>
          <h3 class="events-subtitle">يوم واحد قد يكون بداية شيء مختلف عن كل ما سبق.</h3>
        </div>
        
        <p class="events-desc">
          الفعاليات الحضورية المباشرة مع صفية طاهر هي تجربة مصممة بعناية لتوسع رؤيتك للحياة ولنفسك..
          <br>
          حيث سنعمل معا لتغيير الجمود والصلابة التي يظهر عليها واقعك وهويتك، لتصبح أكثر مرونة، أكثر إشراقا، أكثر وفرة وثقة.
          <br>
          حتى الناس الذين اعتادوا أن يروك بشكل معين، سيسألونك، ماذا فعلت لتتغير هكذا؟ جاهز ؟
          قرار و ضغطة زر و يلا بنا ..
        </p>

        <button class="events-btn">عرض كل الفعاليات</button>
      </div>
    </div>
  </section>
</template>

<style scoped>
.events-section {
  position: relative;
  width: 100%;
  min-height: 856px;
  display: flex;
  align-items: center;
}

.events-bg {
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

.events-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, rgba(0,0,0,0.8) 0%, rgba(0,0,0,0) 100%);
  z-index: 2;
}

/* RTL orientation adjustment */
html[dir="rtl"] .events-overlay {
  background: linear-gradient(270deg, rgba(0,0,0,0.8) 0%, rgba(0,0,0,0) 100%);
}

.events-container {
  position: relative;
  z-index: 3;
  width: 100%;
  display: flex;
  padding: 0 80px;
}

.events-content {
  max-width: 534px;
  display: flex;
  flex-direction: column;
  gap: 32px;
}

.events-header {
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.events-title {
  font-family: var(--sf-font-secondary);
  font-weight: 700;
  font-size: 48px;
  color: #FFFFFF;
}

.events-subtitle {
  font-family: var(--sf-font-body);
  font-weight: 500;
  font-size: 24px;
  color: var(--sf-gold);
}

.events-desc {
  font-family: var(--sf-font-body);
  font-weight: 400;
  font-size: 20px;
  line-height: 1.8;
  color: #FFFFFF;
}

.events-btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 12px 32px;
  border-radius: 100px;
  background-color: var(--sf-teal-deep);
  color: #fff;
  font-family: var(--sf-font-secondary);
  font-weight: 700;
  font-size: 16px;
  width: fit-content;
  transition: background-color 0.3s ease;
}

.events-btn:hover {
  background-color: var(--sf-teal-muted);
}

@media (max-width: 768px) {
  .events-section {
    min-height: 896px;
    align-items: flex-end;
  }
  .events-overlay {
    background: linear-gradient(180deg, rgba(0,0,0,0) 0%, rgba(0,0,0,1) 100%);
  }
  html[dir="rtl"] .events-overlay {
    background: linear-gradient(180deg, rgba(0,0,0,0) 0%, rgba(0,0,0,1) 100%);
  }
  .events-container {
    padding: 48px 24px;
  }
  .events-content {
    gap: 24px;
    text-align: center;
    align-items: center;
  }
  .events-title {
    font-size: 32px;
  }
  .events-subtitle {
    font-size: 16px;
  }
  .events-desc {
    font-size: 16px;
  }
  .events-btn {
    width: 100%;
  }
}
</style>
