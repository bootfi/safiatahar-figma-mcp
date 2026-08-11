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
  height: 400px; /* Figma: 400px */
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
  background-size: 100% 100%; /* Figma: STRETCH with crop */
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
  background-color: rgba(0, 0, 0, 0.2); /* Figma: rgba(0,0,0,0.2) */
  z-index: 2;
}

.cta-container {
  position: relative;
  z-index: 3;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 24px 80px; /* Figma: 24px 80px */
}

.cta-content {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 32px; /* Figma: 32px */
  text-align: center;
  width: 496px; /* Figma: 496px */
}

.cta-title {
  font-family: var(--sf-font-secondary);
  font-weight: 700;
  font-size: 64px; /* Figma: 64px */
  color: #F8F5EF;
}

.cta-btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 8px 16px;
  border-radius: 1000px;
  background: var(--sf-gradient-gold-btn); /* Figma: gold gradient */
  color: var(--sf-dark); /* Figma: #071B1E */
  font-family: var(--sf-font-secondary);
  font-weight: 700;
  font-size: 16px;
  line-height: 1.5em;
  width: 496px; /* Figma: 496px */
  height: 48px;
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
  .cta-container {
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
