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
  padding: 80px 24px 64px;
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  gap: 16px;
}

.voice-title {
  font-family: var(--sf-font-primary);
  font-weight: 900;
  font-size: 48px;
  color: var(--sf-teal-deep);
}

.voice-title__part-2 {
  color: var(--sf-gold);
}

.voice-subtitle {
  font-family: var(--sf-font-body);
  font-weight: 500;
  font-size: 24px;
  color: var(--sf-teal-deep);
  max-width: 800px;
}

.voice-body {
  background: var(--sf-gradient-teal); /* corresponds to fill_e8a64b15 */
  padding: 64px 80px; /* from About Content padding */
  position: relative;
  overflow: hidden; /* Wait, if the image extends out, we might want overflow visible, but let's keep hidden if the parent doesn't allow it, or adjust */
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
  font-family: var(--sf-font-secondary);
  font-weight: 700;
  font-size: 32px; /* Figma: 32 */
  color: var(--sf-gold);
}

.voice-text-2 {
  font-family: var(--sf-font-body);
  font-weight: 400; /* Regular */
  font-size: 32px;
  line-height: 1.5;
  color: var(--sf-bg-primary); /* FCFBF8 */
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
  right: 964px; /* Figma x: 964 -> which is from left. If container is 1440, right is (1440-964-536) = -60px. Wait, let's use left: 964px */
  left: 964px;
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
    padding: 0 24px;
    text-align: center;
    align-items: center;
  }
  .voice-images {
    width: 100%;
    height: 500px;
    margin-top: 64px;
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
    padding: 48px 24px;
  }
  .voice-title {
    font-size: 32px;
  }
  .voice-subtitle {
    font-size: 16px;
  }
  .voice-body {
    padding: 48px 0;
  }
  .voice-text-1, .voice-text-3 {
    font-size: 24px;
  }
  .voice-text-2 {
    font-size: 24px;
  }
  .voice-images {
    height: 400px;
    margin-top: 48px;
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
