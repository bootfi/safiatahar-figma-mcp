<script setup>
const features = [
  {
    title: 'لقاءات شهرية مباشرة',
    desc: 'لقاء مباشر كل شهر مع صفية طاهر للإجابة عن الأسئلة والتعمق في مواضيع الوعي، الحياة، والعلاقات.',
    icon: '/icons/calendar.svg'
  },
  {
    title: 'تأملات حصرية',
    desc: 'تأملات شهرية مصممة لرفع الوعي، تعزيز السلام الداخلي، وترسيخ التحول في الحياة اليومية.',
    icon: '/icons/yoga.svg'
  },
  {
    title: 'دعم و إرشاد',
    desc: 'نصائح وتوجيهات حياتية مهمة لكل فرد في رحلته',
    icon: '/icons/checkmark.svg'
  },
  {
    title: 'أولوية الوصول للمزايا الخاصة',
    desc: 'استفد من أولوية التسجيل في البرامج الجديدة، بالإضافة إلى مزايا ومحتوى حصري مخصص لأعضاء عضوية النخبة فقط.',
    icon: '/icons/sparkles.svg'
  },
  {
    title: 'مجتمع خاص للأعضاء',
    desc: 'انضم إلى مجتمع واع يجمع أشخاصًا يشاركونك رحلة النمو، حيث تجد الدعم، الإلهام، والتشجيع المستمر.',
    icon: '/icons/users.svg'
  }
]
</script>

<template>
  <section class="membership-section" id="membership">
    <div class="membership-container sf-container">
      
      <!-- Right Side: Content -->
      <div class="membership-content">
        <h2 class="membership-title">عضوية النخبة</h2>
        <p class="membership-desc">
          وحدك قد تصل سريعًا، لكن معًا سنصنع مجدا يورث لأجيال ..
          <br>
          حين ادركت قوة ان نمشي بنية موحدة اتجاه حياة أحلامنا قررت ان اصنع مجتمعا راقيا فخما لدعم نوايانا و اهدافنا بشكل مستمر..
          <br>
          و هذا يؤثر بشكل مباشر على إبقاء تردداتنا و بالتالي جذب اعلى و تجسيد اسرع لهويات جديدة
        </p>
        <button class="membership-btn">انضم الآن إلى عضوية النخبة</button>
      </div>

      <!-- Left Side: Features List -->
      <div class="membership-features">
        <div class="feature-item" v-for="(feature, index) in features" :key="index">
          <div class="feature-icon">
            <img :src="feature.icon" :alt="feature.title" />
          </div>
          <div class="feature-text">
            <h4 class="feature-title">{{ feature.title }}</h4>
            <p class="feature-desc">{{ feature.desc }}</p>
          </div>
        </div>
      </div>

    </div>
  </section>
</template>

<style scoped>
.membership-section {
  padding: 80px 0;
  background-color: var(--sf-bg-ivory); /* Mobile says F8F5EF, matches Ivory */
}

.membership-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 64px;
  padding: 0 80px;
}

.membership-content {
  flex: 1;
  display: flex;
  flex-direction: column;
  gap: 32px;
  max-width: 500px;
}

.membership-title {
  font-family: var(--sf-font-secondary);
  font-weight: 700;
  font-size: 48px;
  color: var(--sf-teal-deep);
}

.membership-desc {
  font-family: var(--sf-font-body);
  font-weight: 500;
  font-size: 20px;
  line-height: 1.8;
  color: var(--sf-teal-deep);
}

.membership-btn {
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

.membership-btn:hover {
  opacity: 0.9;
}

.membership-features {
  flex: 1;
  display: flex;
  flex-direction: column;
  gap: 24px;
}

.feature-item {
  display: flex;
  align-items: flex-start;
  gap: 16px;
  padding: 24px;
  background-color: #fff;
  border-radius: 16px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.05);
}

.feature-icon {
  width: 48px;
  height: 48px;
  border-radius: 50%;
  background-color: rgba(9, 59, 51, 0.05);
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
}

.feature-icon img {
  width: 24px;
  height: 24px;
  /* Icon colors might need adjustment if they are black. Typically filter for teal deep: */
  /* filter: brightness(0) saturate(100%) invert(18%) sepia(35%) saturate(836%) hue-rotate(120deg) brightness(97%) contrast(97%); */
}

.feature-text {
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.feature-title {
  font-family: var(--sf-font-secondary);
  font-weight: 700;
  font-size: 20px;
  color: var(--sf-teal-deep);
}

.feature-desc {
  font-family: var(--sf-font-body);
  font-weight: 400;
  font-size: 16px;
  line-height: 1.5;
  color: var(--sf-teal-muted);
}

@media (max-width: 1024px) {
  .membership-container {
    flex-direction: column;
    padding: 0 24px;
  }
  .membership-content {
    max-width: 100%;
    text-align: center;
    align-items: center;
  }
}

@media (max-width: 768px) {
  .membership-section {
    padding: 48px 24px;
  }
  .membership-container {
    padding: 0;
    gap: 32px;
  }
  .membership-title {
    font-size: 32px;
  }
  .membership-desc {
    font-size: 16px;
  }
  .membership-btn {
    width: 100%;
  }
  .feature-item {
    padding: 16px;
  }
  .feature-title {
    font-size: 18px;
  }
  .feature-desc {
    font-size: 14px;
  }
}
</style>
