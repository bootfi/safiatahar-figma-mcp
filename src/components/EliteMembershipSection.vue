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
      
      <!-- Right Side: Features List (Figma: Membership Info on right in RTL) -->
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

      <!-- Left Side: Content (Figma: Membership Benefits) -->
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

    </div>
  </section>
</template>

<style scoped>
.membership-section {
  padding: 0; /* Padding is on container */
  background: var(--sf-gradient-teal); /* Figma: teal gradient, not ivory */
}

.membership-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 64px;
  padding: 48px 80px; /* Figma: 48px 80px */
}

/* Features side (Figma: Membership Info — gold bordered rows) */
.membership-features {
  flex: 1;
  max-width: 577.5px; /* Figma: 577.5px */
  display: flex;
  flex-direction: column;
  gap: 16px; /* Figma: 16px */
}

/* Figma: gold-bordered rows with subtle gold gradient bg */
.feature-item {
  display: flex;
  align-items: flex-start;
  gap: 16px;
  padding: 16px 24px;
  background: linear-gradient(90deg, rgba(184, 151, 95, 0.1) 0%, rgba(247, 229, 155, 0.1) 100%);
  border: 0.6px solid var(--sf-gold);
  border-radius: 24px;
}

.feature-icon {
  width: 48px;
  height: 48px;
  border-radius: 50%;
  background-color: rgba(255, 255, 255, 0.1);
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
}

.feature-icon img {
  width: 24px;
  height: 24px;
  filter: brightness(0) invert(1); /* White icons on teal bg */
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
  color: #F8F5EF; /* Light text on teal bg */
}

.feature-desc {
  font-family: var(--sf-font-body);
  font-weight: 400;
  font-size: 16px;
  line-height: 1.5;
  color: rgba(248, 245, 239, 0.7); /* Slightly muted light text */
}

/* Content / Benefits side */
.membership-content {
  flex: 1;
  max-width: 557.5px; /* Figma: 557.5px */
  display: flex;
  flex-direction: column;
  gap: 32px;
  align-items: center;
}

.membership-title {
  font-family: var(--sf-font-secondary);
  font-weight: 700;
  font-size: 48px;
  color: #F8F5EF; /* Light on teal */
}

.membership-desc {
  font-family: var(--sf-font-body);
  font-weight: 500;
  font-size: 20px;
  line-height: 1.8;
  color: rgba(248, 245, 239, 0.8); /* Slightly muted */
  text-align: center;
}

.membership-btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 8px 16px;
  border-radius: 1000px;
  background: var(--sf-gradient-gold-btn); /* Figma: gold gradient */
  color: var(--sf-dark);
  font-family: var(--sf-font-secondary);
  font-weight: 700;
  font-size: 16px;
  line-height: 1.5em;
  width: 100%; /* Figma: alignSelf stretch */
  height: 48px;
  transition: opacity 0.3s ease;
}

.membership-btn:hover {
  opacity: 0.9;
}

@media (max-width: 1024px) {
  .membership-container {
    flex-direction: column;
    padding: 48px 24px;
  }
  .membership-content {
    max-width: 100%;
    text-align: center;
    align-items: center;
  }
  .membership-features {
    max-width: 100%;
  }
}

@media (max-width: 768px) {
  .membership-section {
    padding: 0;
  }
  .membership-container {
    padding: 48px 24px;
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
