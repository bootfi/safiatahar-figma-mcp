<script setup>
</script>

<template>
  <section class="voice-section">
    <!-- Header part (usually white bg or transparent) -->
    <div class="voice-header sf-container">
      <h2 class="voice-title">
        <span class="voice-title__part-1">صوت قوي، ملهمة تغيير و </span>
        <span class="voice-title__part-2">معلمة استثنائية..</span>
      </h2>
      <p class="voice-subtitle">ان كنت تبحث عن ذلك الصوت الذي يوقظ اجزاءك المنسية و المخدرة فأنت في المكان الصح</p>
    </div>

    <!-- Teal Gradient part -->
    <div class="voice-body">
      <div class="voice-content-wrapper sf-container">
        
        <div class="voice-text-box">
          <p class="voice-text-1">أنا صفية،</p>
          <p class="voice-text-2">
            و أعدك ان دخولك هنا ليس كخروجك، فالشيء المختلف و السحري الذي تبحث عنه لتختبر حياة اكثر معنى و جمالا و وفرة. موجود هنا
          </p>
          <p class="voice-text-3">أمسك يدي و دعنا نكتشف..</p>
        </div>

        <div class="voice-images">
          <img src="/images/safia-photo-tall.png" alt="Safia Tahar" class="voice-img-tall" />
          <img src="/images/safia-photo-small.png" alt="Safia Tahar" class="voice-img-small" />
        </div>

      </div>
    </div>
  </section>
</template>

<style scoped>
.voice-section {
  display: flex;
  flex-direction: column;
  background-color: var(--sf-bg-primary);
}

.voice-header {
  padding: var(--spacing-3xl) var(--spacing-md) var(--spacing-2xl); /* 80px 24px 64px */
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  gap: var(--spacing-sm);                /* 16px — Spacing-sm */
}

.voice-title {
  font-family: var(--sf-font-primary);
  font-weight: var(--font-weight-extrabold);  /* 900 */
  font-size: var(--font-size-xl);             /* 48px — Font-size-xl */
  color: var(--color-primary-500);
}

.voice-title__part-2 {
  color: var(--color-accent-500);
}

.voice-subtitle {
  font-family: var(--font-family-secondary);  /* Tajawal */
  font-weight: var(--font-weight-regular);
  font-size: var(--font-size-base);           /* 24px — Font-size-base */
  color: var(--color-primary-500);
  max-width: 800px;
}

.voice-body {
  background: var(--sf-gradient-teal);
  padding: var(--spacing-2xl) var(--spacing-3xl); /* 64px 80px */
  position: relative;
  overflow: hidden;
}

.voice-content-wrapper {
  display: flex;
  justify-content: space-between;
  align-items: center;
  position: relative;
  max-width: 1440px;
  margin: 0 auto;
}

.voice-text-box {
  width: 708px; /* From Stats Section width */
  display: flex;
  flex-direction: column;
  gap: 18px;
  z-index: 2;
  align-items: flex-end; /* RTL right alignment */
}

.voice-text-1, .voice-text-3 {
  font-family: var(--font-family-primary);  /* Noto Naskh Arabic */
  font-weight: var(--font-weight-bold);
  font-size: var(--font-size-xl);            /* 48px — Font-size-xl */
  background: var(--sf-gradient-gold-vertical);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  color: transparent;
}

.voice-text-2 {
  font-family: var(--font-family-secondary); /* Tajawal */
  font-weight: var(--font-weight-regular);
  font-size: var(--font-size-lg);            /* 32px — Font-size-lg */
  line-height: 1.5;
  color: var(--color-white-400);
  text-align: right;
}


.voice-images {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  pointer-events: none;
  z-index: 1;
}

.voice-img-tall {
  position: absolute;
  top: -163px;
  right: 0;
  left: auto;
  width: 536px;
  height: 803px;
  border-radius: 20px;
  object-fit: cover;
  box-shadow: 0 20px 40px rgba(0,0,0,0.2);
}

.voice-img-small {
  position: absolute;
  top: 311px;
  left: -60px; /* Figma x: -60 */
  width: 358px;
  height: 409px;
  border-radius: 20px;
  object-fit: cover;
  box-shadow: 0 20px 40px rgba(0,0,0,0.2);
}

@media (max-width: 1024px) {
  .voice-content-wrapper {
    flex-direction: column;
  }
  .voice-text-box {
    width: 100%;
    padding: 0 var(--spacing-md);          /* 0 24px */
    text-align: center;
    align-items: center;
  }
  .voice-images {
    width: 100%;
    height: 500px;
    margin-top: var(--spacing-2xl);        /* 64px */
  }
  .voice-img-tall {
    left: 50%;
    transform: translateX(-50%);
  }
  .voice-img-small {
    right: auto;
    left: 10%;
  }
}

@media (max-width: 768px) {
  .voice-header {
    padding: var(--spacing-xl) var(--spacing-md); /* 48px 24px */
  }
  .voice-title {
    font-size: var(--font-size-lg);          /* 32px */
  }
  .voice-subtitle {
    font-size: var(--font-size-sm);          /* 16px */
  }
  .voice-body {
    padding: var(--spacing-xl) 0;            /* 48px 0 */
  }
  .voice-text-1, .voice-text-3 {
    font-size: var(--font-size-base);        /* 24px */
  }
  .voice-text-2 {
    font-size: var(--font-size-base);        /* 24px */
  }
  .voice-images {
    height: 400px;
    margin-top: var(--spacing-xl);           /* 48px */
  }
  .voice-img-tall {
    width: 246px;
    top: -40px;
    left: 40%;
  }
  .voice-img-small {
    width: 227px;
    bottom: 0;
    right: -20px;
    left: auto;
  }
}
</style>
