<script setup>
</script>

<template>
  <section class="about-section" id="about">
    <div class="about-container sf-container">
      <div class="about-content">
        <h2 class="about-title">من هي صفية طاهر؟</h2>
        <div class="about-desc">
          <p class="about-desc__part-1">صفية طاهر معلمة وعي، متحدثة و سيدة أعمال. </p>
          <p class="about-desc__part-2">جعلت من تطوير الذات و رفع جودة الحياة رسالة سامية لها لتأخذ بيدك و تختبر بعمق معنى أن "هناك شيء أكبر ينتظرك". مهمتها انها ترشدك و تريك ما هو فعلا متاح لك، من خلال كورسات حضورية و اونلاين لتعطيك تقنيات و اسرار عملت بها شخصيا و غيرت واقعها تماما، وتهديك ملخص كيف انتقلت من موظفة ب 160 $ إلى ميليونيرة و اسم مرتبط " بالثراء و الالهام"</p>
        </div>
        <div class="about-stats">
          <div class="stat-box">
            <span class="stat-value">+8</span>
            <span class="stat-label">سنوات خبرة</span>
          </div>
          <div class="stat-box">
            <span class="stat-value">+15k</span>
            <span class="stat-label">ساعة تدريبية</span>
          </div>
          <div class="stat-box">
            <span class="stat-value">+30k</span>
            <span class="stat-label">متدرب حول العالم</span>
          </div>
        </div>
        <button class="about-btn">
          تعرف على صفية
          <img src="/icons/arrow-left.svg" alt="" aria-hidden="true" class="btn-icon" />
        </button>
      </div>
      <div class="about-image-wrapper">
        <div class="about-image-deco"></div>
        <img class="about-image" src="/images/about-photo.png" alt="صفية طاهر" />
      </div>
    </div>
  </section>
</template>

<style scoped>
/* Section: padding 64px 80px */
.about-section {
  padding: var(--spacing-2xl) var(--spacing-3xl);
  background-color: var(--color-surface-main);
}
/* Container: flex row, gap 64px */
.about-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: var(--spacing-2xl);
}
/* Content: flex column, gap 32px */
.about-content {
  flex: 1;
  display: flex;
  flex-direction: column;
  gap: var(--spacing-lg);
  max-width: 636px;
}
.about-title {
  font-family: var(--font-family-secondary);
  font-weight: var(--font-weight-medium);
  font-size: var(--font-size-lg);
  color: var(--color-accent-500);
}
/* Desc: flex column, gap 8px */
.about-desc {
  display: flex;
  flex-direction: column;
  gap: var(--spacing-xs);
}
.about-desc__part-1 {
  font-family: var(--font-family-secondary);
  font-weight: var(--font-weight-bold);
  font-size: var(--font-size-base);
  line-height: 1.5;
  color: var(--color-primary-400);
  margin: 0;
}
.about-desc__part-2 {
  font-family: var(--font-family-secondary);
  font-weight: var(--font-weight-medium);
  font-size: var(--font-size-body);
  line-height: 1.8;
  color: var(--color-text-description);
  margin: 0;
}
/* Stats: flex row, gap 24px */
.about-stats {
  display: flex;
  gap: var(--spacing-md);
}
/* Stat card: padding 16px 24px, radius 16px */
.stat-box {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: var(--spacing-xs);
  padding: var(--spacing-sm) var(--spacing-md);
  border-radius: var(--radius-mid-mobile);
  border: 3px solid var(--color-surface-transparent-accent);
  min-width: 140px;
}
.stat-value {
  font-family: var(--sf-font-english);
  font-weight: var(--font-weight-regular);
  font-size: var(--font-size-lg);
  color: var(--color-primary-500);
}
.stat-label {
  font-family: var(--font-family-secondary);
  font-weight: var(--font-weight-medium);
  font-size: var(--font-size-sm);
  color: var(--color-primary-400);
}
/* Button: padding 8px 16px, radius full, height 48px */
.about-btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: var(--spacing-xxs);
  padding: var(--spacing-xs) var(--spacing-sm);
  border-radius: var(--radius-full);
  background: var(--sf-gradient-gold-btn);
  color: var(--color-black-500);
  font-family: var(--font-family-primary);
  font-weight: var(--font-weight-bold);
  font-size: var(--font-size-sm);
  line-height: 1.5em;
  width: 292px;
  height: var(--spacing-xl);
  transition: opacity 0.3s ease;
}
.about-btn:hover { opacity: 0.9; }
.btn-icon { width: 20px; height: 20px; }
/* Image wrapper */
.about-image-wrapper {
  position: relative;
  width: 519px;
  height: 597px;
  flex-shrink: 0;
}
.about-image-deco {
  position: absolute;
  top: 14px;
  left: 0;
  width: 507px;
  height: 583px;
  border-radius: var(--radius-mid);
  border: 1px solid var(--color-accent-500);
  z-index: 1;
}
.about-image {
  position: absolute;
  top: 0;
  left: 10px;
  width: 509px;
  height: 583px;
  border-radius: var(--radius-mid);
  object-fit: cover;
  z-index: 2;
}
@media (max-width: 1024px) {
  .about-container { flex-direction: column; text-align: center; }
  .about-content { align-items: center; }
  .about-desc__part-1, .about-desc__part-2 { text-align: center; }
  .about-stats { flex-wrap: wrap; justify-content: center; }
}
@media (max-width: 768px) {
  .about-section { padding: var(--spacing-xl) var(--spacing-md); }
  .about-title { font-size: var(--font-size-base); }
  .about-desc__part-1 { font-size: var(--font-size-body); }
  .about-desc__part-2 { font-size: var(--font-size-sm); }
  .about-image-wrapper { width: 334px; height: 329px; }
  .about-image-deco { width: 334px; height: 321px; top: 7px; left: 0; }
  .about-image { width: 321px; height: 321px; top: 0; left: 8px; }
  .about-btn { width: 292px; }
  .about-stats { flex-direction: column; width: 100%; }
  .stat-box { flex-direction: row; justify-content: space-between; padding: var(--spacing-sm) var(--spacing-md); }
}
</style>
