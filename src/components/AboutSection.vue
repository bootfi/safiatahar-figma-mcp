<script setup>
</script>

<template>
  <section class="about-section" id="about">
    <div class="about-container sf-container">
      
      <!-- Right Side: Text & Stats -->
      <div class="about-content">
        <h2 class="about-title">من هي صفية طاهر؟</h2>
        
        <div class="about-desc">
          <p class="about-desc__part-1">صفية طاهر معلمة وعي، متحدثة و سيدة أعمال. </p>
          <p class="about-desc__part-2">
            جعلت من تطوير الذات و رفع جودة الحياة رسالة سامية لها لتأخذ بيدك و تختبر بعمق معنى أن "هناك شيء أكبر ينتظرك". مهمتها انها ترشدك و تريك ما هو فعلا متاح لك، من خلال كورسات حضورية و اونلاين لتعطيك تقنيات و اسرار عملت بها شخصيا و غيرت واقعها تماما، وتهديك ملخص كيف انتقلت من موظفة ب 160 $ إلى ميليونيرة و اسم مرتبط " بالثراء و الالهام"
          </p>
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

      <!-- Left Side: Image -->
      <div class="about-image-wrapper">
        <div class="about-image-deco"></div>
        <img class="about-image" src="/images/about-photo.png" alt="صفية طاهر" />
      </div>

    </div>
  </section>
</template>

<style scoped>
.about-section {
  padding: 64px 80px;
  background-color: var(--sf-bg-primary);
}

.about-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 64px;
}

.about-content {
  flex: 1;
  display: flex;
  flex-direction: column;
  gap: 32px;
  max-width: 636px;
}

.about-title {
  font-family: var(--sf-font-body);
  font-weight: 500;
  font-size: 32px;
  color: var(--sf-gold);
}

.about-desc {
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.about-desc__part-1 {
  font-family: var(--sf-font-body);
  font-weight: 700;
  font-size: 24px;
  line-height: 1.5;
  color: var(--sf-teal-muted);
  margin: 0;
}

.about-desc__part-2 {
  font-family: var(--sf-font-body);
  font-weight: 500;
  font-size: 20px;
  line-height: 1.8;
  color: var(--sf-teal-mid);
  margin: 0;
}

.about-stats {
  display: flex;
  gap: 24px;
  margin-top: 16px;
}

.stat-box {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 8px;
  padding: 16px 24px;
  border-radius: 16px;
  border: 3px solid rgba(184, 151, 95, 0.2); /* sf-gold with opacity */
  min-width: 140px;
}

.stat-value {
  font-family: var(--sf-font-english);
  font-weight: 400;
  font-size: 32px;
  color: var(--sf-teal-deep);
}

.stat-label {
  font-family: var(--sf-font-body);
  font-weight: 500;
  font-size: 16px;
  color: var(--sf-teal-muted);
}

.about-btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 4px;
  padding: 8px 16px;
  border-radius: 1000px;
  background: var(--sf-gradient-gold-btn);
  color: var(--sf-dark);
  font-family: var(--sf-font-secondary);
  font-weight: 700;
  font-size: 16px;
  line-height: 1.5em;
  width: 292px;
  height: 48px;
  transition: opacity 0.3s ease;
}

.about-btn:hover {
  opacity: 0.9;
}

.btn-icon {
  width: 20px;
  height: 20px;
}

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
  border-radius: 24px;
  border: 1px solid var(--sf-gold); /* Figma uses dd64a1a5 which maps to sf-gold */
  z-index: 1;
}

.about-image {
  position: absolute;
  top: 0;
  left: 10px; /* Figma x: 10 */
  width: 509px;
  height: 583px;
  border-radius: 24px;
  object-fit: cover;
  z-index: 2;
}

@media (max-width: 1024px) {
  .about-container {
    flex-direction: column;
    text-align: center;
  }
  .about-content {
    align-items: center;
  }
  .about-desc__part-1, .about-desc__part-2 {
    text-align: center;
  }
  .about-stats {
    flex-wrap: wrap;
    justify-content: center;
  }
}

@media (max-width: 768px) {
  .about-section {
    padding: 48px 24px;
  }
  .about-title {
    font-size: 24px;
  }
  .about-desc__part-1 {
    font-size: 20px;
  }
  .about-desc__part-2 {
    font-size: 16px;
  }
  .about-image-wrapper {
    width: 334px;
    height: 329px;
  }
  .about-image-deco {
    width: 334px;
    height: 321px;
    top: 7px;
    left: 0;
  }
  .about-image {
    width: 321px;
    height: 321px;
    top: 0;
    left: 8px;
  }
  .about-btn {
    width: 292px;
  }
  .about-stats {
    flex-direction: column;
    width: 100%;
  }
  .stat-box {
    flex-direction: row;
    justify-content: space-between;
    padding: 16px 24px;
  }
}
</style>
