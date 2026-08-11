<script setup>
</script>

<template>
  <section class="cta-banner-section">
    <div class="cta-bg"></div>
    <div class="cta-overlay"></div>
    
    <div class="cta-container sf-container">
      <div class="cta-content">
        <h2 class="cta-title">رحلتك تبدأ بقرارٍ واحد</h2>
        <button class="cta-btn">ابدأ الآن</button>
      </div>
    </div>
  </section>
</template>

<style scoped>
.cta-banner-section {
  position: relative;
  width: 100%;
  height: 600px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.cta-bg {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: url('/images/cta-banner-bg.png');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  z-index: 1;
}

.cta-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.4); /* Adjust opacity for readable text */
  z-index: 2;
}

.cta-container {
  position: relative;
  z-index: 3;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.cta-content {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 48px;
  text-align: center;
}

.cta-title {
  font-family: var(--sf-font-secondary);
  font-weight: 700;
  font-size: 48px;
  color: #FFFFFF;
}

.cta-btn {
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
  transition: opacity 0.3s ease;
}

.cta-btn:hover {
  opacity: 0.9;
}

@media (max-width: 768px) {
  .cta-banner-section {
    height: 400px;
    padding: 24px;
  }
  .cta-content {
    width: 100%;
    gap: 32px;
  }
  .cta-title {
    font-size: 32px;
  }
  .cta-btn {
    width: 100%;
  }
}
</style>
