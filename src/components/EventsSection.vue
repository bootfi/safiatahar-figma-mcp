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
    ? getAssetUrl('/images/events-mobile-bg.png') 
    : getAssetUrl('/images/events-bg.png')
})
</script>

<template>
  <section class="events-section" id="events">
    <div class="events-bg" :style="{ backgroundImage: `url(${bgImage})` }"></div>
    <div class="events-overlay"></div>
    
    <div class="events-container sf-container">
      <div class="events-content">
        <div class="events-header">
          <!-- Figma: subtitle first (small text), then title (big text) -->
          <p class="events-label">الفعاليات الحضورية لعام 2026</p>
          <h2 class="events-title">يوم واحد قد يكون بداية شيء مختلف عن كل ما سبق.</h2>
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
  /* Figma: linear-gradient(-90deg, transparent 42%, black 100%) = RTL dark on right */
  background: linear-gradient(270deg, rgba(0,0,0,0) 42%, rgba(0,0,0,1) 100%);
  z-index: 2;
}

.events-container {
  position: relative;
  z-index: 3;
  width: 100%;
  display: flex;
  padding: var(--spacing-xl) var(--spacing-3xl); /* 48px 80px — Spacing-xl Spacing-3xl */
}

.events-content {
  max-width: 534px;
  display: flex;
  flex-direction: column;
  gap: 51px; /* Figma: gap 51px — closest to Spacing-xl 48px */
}

.events-header {
  display: flex;
  flex-direction: column;
  gap: var(--spacing-xs);  /* 8px — Spacing-xs */
}

/* Figma: small label first — Tajawal Regular 400 20px */
.events-label {
  font-family: var(--font-family-secondary);  /* Tajawal */
  font-weight: var(--font-weight-regular);    /* 400 */
  font-size: var(--font-size-body);           /* 20px — Font-size-body */
  color: var(--color-white-400);
  margin: 0;
}

.events-title {
  font-family: var(--font-family-primary);    /* Noto Naskh Arabic */
  font-weight: var(--font-weight-bold);       /* 700 */
  font-size: var(--font-size-xl);             /* 48px — Font-size-xl */
  color: var(--color-white-400);
}

.events-desc {
  font-family: var(--font-family-secondary);  /* Tajawal */
  font-weight: var(--font-weight-medium);     /* 500 */
  font-size: var(--font-size-lg);             /* 32px — Font-size-lg */
  line-height: 1.5;
  color: var(--color-white-400);
  margin: 0;
}

.events-btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: var(--spacing-xs) var(--spacing-sm); /* 8px 16px */
  border-radius: var(--radius-full);            /* 1000px — Radius-full */
  background: var(--sf-gradient-gold-btn);
  color: var(--color-black-500);
  font-family: var(--font-family-primary);      /* Noto Naskh Arabic */
  font-weight: var(--font-weight-bold);         /* 700 */
  font-size: var(--font-size-sm);               /* 16px — Font-size-sm */
  line-height: 1.5em;
  height: var(--spacing-xl);                    /* 48px — Spacing-xl */
  width: 100%;
  transition: opacity 0.3s ease;
}

.events-btn:hover {
  opacity: 0.9;
}

@media (max-width: 768px) {
  .events-section {
    min-height: 896px;
    align-items: flex-end;
  }
  .events-overlay {
    background: linear-gradient(180deg, rgba(0,0,0,0) 0%, rgba(0,0,0,1) 100%);
  }
  .events-container {
    padding: var(--spacing-xl) var(--spacing-md); /* 48px 24px */
  }
  .events-content {
    gap: var(--spacing-lg);                       /* 32px */
    text-align: center;
    align-items: center;
  }
  .events-title {
    font-size: var(--font-size-lg);               /* 32px */
  }
  .events-label {
    font-size: var(--font-size-sm);               /* 16px */
  }
  .events-desc {
    font-size: var(--font-size-sm);               /* 16px */
  }
  .events-btn {
    width: 100%;
  }
}
</style>
