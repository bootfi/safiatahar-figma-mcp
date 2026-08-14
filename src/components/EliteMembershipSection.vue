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
  gap: var(--spacing-2xl);               /* 64px — Spacing-2xl */
  padding: var(--spacing-xl) var(--spacing-3xl); /* 48px 80px */
}

/* Features side (Figma: Membership Info — gold bordered rows) */
.membership-features {
  flex: 1;
  max-width: 577.5px;
  display: flex;
  flex-direction: column;
  gap: var(--spacing-sm);                /* 16px — Spacing-sm */
}

/* Figma: gold-bordered rows with subtle gold gradient bg */
.feature-item {
  display: flex;
  align-items: flex-start;
  gap: var(--spacing-sm);                /* 16px — Spacing-sm */
  padding: var(--spacing-sm) var(--spacing-md); /* 16px 24px */
  background: linear-gradient(90deg, rgba(184, 151, 95, 0.1) 0%, rgba(247, 229, 155, 0.1) 100%);
  border: 0.6px solid var(--color-accent-500);
  border-radius: var(--radius-mid);      /* 24px — Radius-mid */
}

.feature-icon {
  width: var(--spacing-xl);              /* 48px — Spacing-xl */
  height: var(--spacing-xl);
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
  gap: var(--spacing-xs);               /* 8px — Spacing-xs */
}

.feature-title {
  font-family: var(--font-family-primary);  /* Noto Naskh Arabic */
  font-weight: var(--font-weight-bold);
  font-size: var(--font-size-body);         /* 20px — Font-size-body */
  color: var(--color-white-400);
}

.feature-desc {
  font-family: var(--font-family-secondary); /* Tajawal */
  font-weight: var(--font-weight-regular);
  font-size: var(--font-size-sm);            /* 16px — Font-size-sm */
  line-height: 1.5;
  color: rgba(248, 245, 239, 0.7);
}

/* Content / Benefits side */
.membership-content {
  flex: 1;
  max-width: 557.5px;
  display: flex;
  flex-direction: column;
  gap: var(--spacing-lg);               /* 32px — Spacing-lg */
  align-items: center;
}

.membership-title {
  font-family: var(--font-family-primary);  /* Noto Naskh Arabic */
  font-weight: var(--font-weight-bold);
  font-size: var(--font-size-xl);           /* 48px — Font-size-xl */
  color: var(--color-white-400);
}

.membership-desc {
  font-family: var(--font-family-secondary); /* Tajawal */
  font-weight: var(--font-weight-medium);
  font-size: var(--font-size-body);          /* 20px — Font-size-body */
  line-height: 1.8;
  color: rgba(248, 245, 239, 0.8);
  text-align: center;
}

.membership-btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: var(--spacing-xs) var(--spacing-sm); /* 8px 16px */
  border-radius: var(--radius-full);            /* 1000px — Radius-full */
  background: var(--sf-gradient-gold-btn);
  color: var(--color-black-500);
  font-family: var(--font-family-primary);
  font-weight: var(--font-weight-bold);
  font-size: var(--font-size-sm);               /* 16px — Font-size-sm */
  line-height: 1.5em;
  width: 100%;
  height: var(--spacing-xl);                    /* 48px — Spacing-xl */
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
    padding: var(--spacing-xl) var(--spacing-md); /* 48px 24px */
    gap: var(--spacing-lg);                        /* 32px */
  }
  .membership-title {
    font-size: var(--font-size-lg);                /* 32px */
  }
  .membership-desc {
    font-size: var(--font-size-sm);                /* 16px */
  }
  .membership-btn {
    width: 100%;
  }
  .feature-item {
    padding: var(--spacing-sm);                    /* 16px */
  }
  .feature-title {
    font-size: var(--font-size-body);              /* 20px (was 18px, closest token) */
  }
  .feature-desc {
    font-size: var(--font-size-xs);                /* 12px (was 14px, closest token) */
  }
}
</style>
