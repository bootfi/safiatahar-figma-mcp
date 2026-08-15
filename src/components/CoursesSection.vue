<script setup>
import { ref } from 'vue'
import { getAssetUrl } from '../utils/assets.js'

const courses = [
  {
    id: 1,
    title: 'اصنع المعجزات',
    description: 'القيم هي الأساس الذي تبنى عليه حياة متناسقة مع الحقيقة',
    image: getAssetUrl('/images/course-values.png'),
    tag: '5 مستويات'
  },
  {
    id: 2,
    title: 'المعجزات',
    description: 'ميلاد المعجزة من الداخل .. حيث تولد النسخة الخارقة من جديد',
    image: getAssetUrl('/images/course-miracles.png'),
    tag: '5 مستويات'
  },
  {
    id: 3,
    title: 'عهد الثراء الواحد',
    description: 'رحلة تحول عميقة تأخذك إلى أعماق ذاتك، لتكتشف قدراتك فتعيد بناء نفسك بوعي جديد.',
    image: getAssetUrl('/images/course-wealth.png'),
    tag: '5 مستويات'
  }
]

const scrollContainer = ref(null)

const scrollLeft = () => {
  if (scrollContainer.value) {
    scrollContainer.value.scrollBy({ left: -360, behavior: 'smooth' })
  }
}

const scrollRight = () => {
  if (scrollContainer.value) {
    scrollContainer.value.scrollBy({ left: 360, behavior: 'smooth' })
  }
}
</script>

<template>
  <section class="courses-section" id="courses">
    <div class="courses-container sf-container">
      
      <div class="courses-header">
        <div class="header-text">
          <h2 class="courses-title">الدورات</h2>
          <p class="courses-subtitle">لكل برنامج هنا قوته وطريقته في إحداث تحول مختلف من الداخل</p>
        </div>
        <div class="header-nav">
          <button class="nav-btn" @click="scrollRight">
            <img :src="getAssetUrl('/icons/arrow-right.svg')" alt="Right" />
          </button>
          <button class="nav-btn" @click="scrollLeft">
            <img :src="getAssetUrl('/icons/arrow-left.svg')" alt="Left" />
          </button>
        </div>
      </div>

      <div class="courses-list" ref="scrollContainer">
        <div class="course-card" v-for="course in courses" :key="course.id">
          
          <div class="card-image-wrapper">
            <img :src="course.image" :alt="course.title" class="card-image" />
            <button class="card-fav-btn">
              <img :src="getAssetUrl('/icons/heart.svg')" alt="Favorite" />
            </button>
          </div>

          <div class="card-content">
            <div class="card-tag">
              <span class="tag-text">{{ course.tag }}</span>
            </div>
            
            <h3 class="card-title">{{ course.title }}</h3>
            <p class="card-desc">{{ course.description }}</p>

            <button class="card-btn">
              عرض التفاصيل
              <img :src="getAssetUrl('/icons/arrow-left.svg')" alt="" aria-hidden="true" class="btn-icon" />
            </button>
          </div>

        </div>
      </div>

    </div>
  </section>
</template>

<style scoped>
.courses-section {
  padding: var(--spacing-3xl) 0;             /* 80px 0 */
  background-color: var(--color-surface-main);
}

.courses-container {
  display: flex;
  flex-direction: column;
  gap: var(--spacing-xl);                    /* 48px — Spacing-xl */
  max-width: 1280px;
  margin: 0 auto;
  padding: 0 var(--spacing-md);              /* 0 24px */
}

.courses-header {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
}

.header-text {
  display: flex;
  flex-direction: column;
  gap: var(--spacing-xs);                    /* 8px — Spacing-xs */
}

.courses-title {
  font-family: var(--font-family-primary);   /* Noto Naskh Arabic */
  font-weight: var(--font-weight-bold);
  font-size: var(--font-size-xl);            /* 48px — Font-size-xl */
  color: var(--color-accent-500);
}

.courses-subtitle {
  font-family: var(--font-family-secondary); /* Tajawal */
  font-weight: var(--font-weight-regular);
  font-size: var(--font-size-body);          /* 20px — Font-size-body */
  color: var(--color-primary-500);
}

.header-nav {
  display: flex;
  gap: var(--spacing-sm);                    /* 16px — Spacing-sm */
}

.nav-btn {
  width: var(--spacing-xl);                  /* 48px — Spacing-xl */
  height: var(--spacing-xl);
  border-radius: var(--radius-full);         /* 1000px — Radius-full */
  border: none;
  display: flex;
  align-items: center;
  justify-content: center;
  background: var(--sf-gradient-gold-btn);
  transition: all 0.3s ease;
}

.nav-btn:hover {
  opacity: 0.9;
  transform: scale(1.05);
}

.nav-btn img {
  width: 20px;
  height: 20px;
}

.courses-list {
  display: flex;
  gap: var(--spacing-md);                    /* 24px — Spacing-md */
  overflow-x: auto;
  padding-bottom: var(--spacing-md);         /* 24px (for shadow) */
  scrollbar-width: none;
}

.courses-list::-webkit-scrollbar {
  display: none; /* Chrome, Safari, Edge */
}

.course-card {
  min-width: 349px;
  height: 495px;
  background-color: var(--color-surface-main);
  border-radius: var(--radius-mid);          /* 24px — Radius-mid */
  overflow: hidden;
  display: flex;
  flex-direction: column;
  border: 1px solid var(--color-accent-500);
  box-shadow: 0 0 20px rgba(0, 0, 0, 0.05);
}

.card-image-wrapper {
  position: relative;
  width: 100%;
  height: 334px;
  padding: var(--spacing-sm);                /* 16px — Spacing-sm */
}

.card-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: var(--radius-mid-mobile);   /* 16px — Radius-mid-mobile */
}

.card-fav-btn {
  position: absolute;
  top: 32px;
  left: 32px;
  width: 40px;
  height: 40px;
  border-radius: 50%;
  background: rgba(255, 255, 255, 0.8);
  display: flex;
  align-items: center;
  justify-content: center;
}

.card-content {
  padding: var(--spacing-md);                /* 24px — Spacing-md */
  display: flex;
  flex-direction: column;
  gap: var(--spacing-sm);                    /* 16px — Spacing-sm */
}

.card-tag {
  display: inline-block;
  padding: var(--spacing-xxs) 12px;          /* 4px 12px */
  background: var(--color-surface-transparent-primary);
  border-radius: var(--radius-full);         /* 1000px — Radius-full */
  width: fit-content;
}

.tag-text {
  font-family: var(--sf-font-body);
  font-weight: 500;
  font-size: 14px;
  color: var(--sf-teal-deep);
}

.card-title {
  font-family: var(--font-family-primary);   /* Noto Naskh Arabic */
  font-weight: var(--font-weight-bold);
  font-size: var(--font-size-lg);            /* 32px — Font-size-lg */
  color: var(--color-primary-500);
}

.card-desc {
  font-family: var(--font-family-secondary); /* Tajawal */
  font-weight: var(--font-weight-medium);
  font-size: var(--font-size-sm);            /* 16px — Font-size-sm */
  line-height: 1.5;
  color: var(--color-primary-400);
  flex-grow: 1;
}

.card-btn {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 12px var(--spacing-md);           /* 12px 24px (12 has no token) */
  border-radius: var(--radius-full);         /* 1000px — Radius-full */
  border: 1px solid var(--color-primary-500);
  background: transparent;
  color: var(--color-primary-500);
  font-family: var(--font-family-primary);
  font-weight: var(--font-weight-bold);
  font-size: var(--font-size-sm);            /* 16px — Font-size-sm */
  transition: all 0.3s ease;
  margin-top: var(--spacing-sm);             /* 16px — Spacing-sm */
}

.card-btn:hover {
  background-color: var(--sf-teal-deep);
  color: #fff;
}

.card-btn:hover .btn-icon {
  filter: brightness(0) invert(1);
}

.btn-icon {
  width: 24px;
  height: 24px;
  transition: filter 0.3s ease;
}

@media (max-width: 768px) {
  .courses-header {
    flex-direction: column;
    align-items: flex-start;
    gap: var(--spacing-md);                  /* 24px */
  }
  .courses-title {
    font-size: var(--font-size-lg);          /* 32px */
  }
  .courses-subtitle {
    font-size: var(--font-size-sm);          /* 16px */
  }
  .header-nav {
    display: none;
  }
  .course-card {
    min-width: 244px;
  }
  .card-image-wrapper {
    height: 240px;
  }
  .card-title {
    font-size: var(--font-size-base);        /* 24px */
  }
  .card-desc {
    font-size: var(--font-size-xs);          /* 12px (was 14 — closest token) */
  }
}
</style>
