<script setup>
import { ref, onMounted } from 'vue'

const courses = [
  {
    id: 1,
    title: 'اصنع المعجزات',
    description: 'القيم هي الأساس الذي تبنى عليه حياة متناسقة مع الحقيقة',
    image: '/images/course-values.png',
    tag: '5 مستويات'
  },
  {
    id: 2,
    title: 'المعجزات',
    description: 'ميلاد المعجزة من الداخل .. حيث تولد النسخة الخارقة من جديد',
    image: '/images/course-miracles.png',
    tag: '5 مستويات'
  },
  {
    id: 3,
    title: 'عهد الثراء الواحد',
    description: 'رحلة تحول عميقة تأخذك إلى أعماق ذاتك، لتكتشف قدراتك فتعيد بناء نفسك بوعي جديد.',
    image: '/images/course-wealth.png',
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
            <img src="/icons/arrow-right.svg" alt="Right" />
          </button>
          <button class="nav-btn" @click="scrollLeft">
            <img src="/icons/arrow-left.svg" alt="Left" />
          </button>
        </div>
      </div>

      <div class="courses-list" ref="scrollContainer">
        <div class="course-card" v-for="course in courses" :key="course.id">
          
          <div class="card-image-wrapper">
            <img :src="course.image" :alt="course.title" class="card-image" />
            <button class="card-fav-btn">
              <img src="/icons/heart.svg" alt="Favorite" />
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
              <img src="/icons/arrow-left.svg" alt="" aria-hidden="true" class="btn-icon" />
            </button>
          </div>

        </div>
      </div>

    </div>
  </section>
</template>

<style scoped>
.courses-section {
  padding: 80px 0;
  background-color: var(--sf-bg-primary);
}

.courses-container {
  display: flex;
  flex-direction: column;
  gap: 48px;
  max-width: 1280px;
  margin: 0 auto;
  padding: 0 24px;
}

.courses-header {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
}

.header-text {
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.courses-title {
  font-family: var(--sf-font-secondary);
  font-weight: 700;
  font-size: 48px;
  color: var(--sf-teal-deep);
}

.courses-subtitle {
  font-family: var(--sf-font-body);
  font-weight: 500;
  font-size: 24px;
  color: var(--sf-teal-deep);
}

.header-nav {
  display: flex;
  gap: 16px;
}

.nav-btn {
  width: 48px;
  height: 48px;
  border-radius: 50%;
  border: 1px solid var(--sf-teal-deep);
  display: flex;
  align-items: center;
  justify-content: center;
  background: transparent;
  transition: all 0.3s ease;
}

.nav-btn:hover {
  background-color: var(--sf-teal-deep);
}

.nav-btn:hover img {
  filter: brightness(0) invert(1);
}

.courses-list {
  display: flex;
  gap: 24px;
  overflow-x: auto;
  padding-bottom: 24px; /* for shadow */
  scrollbar-width: none; /* Firefox */
}

.courses-list::-webkit-scrollbar {
  display: none; /* Chrome, Safari, Edge */
}

.course-card {
  min-width: 349px;
  background-color: var(--sf-bg-ivory);
  border-radius: 24px;
  overflow: hidden;
  display: flex;
  flex-direction: column;
  border: 1px solid rgba(0,0,0,0.05);
}

.card-image-wrapper {
  position: relative;
  width: 100%;
  height: 334px;
  padding: 16px;
}

.card-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 16px;
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
  padding: 24px;
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.card-tag {
  display: inline-block;
  padding: 4px 12px;
  background: rgba(9, 59, 51, 0.1);
  border-radius: 100px;
  width: fit-content;
}

.tag-text {
  font-family: var(--sf-font-body);
  font-weight: 500;
  font-size: 14px;
  color: var(--sf-teal-deep);
}

.card-title {
  font-family: var(--sf-font-secondary);
  font-weight: 700;
  font-size: 32px;
  color: var(--sf-teal-deep);
}

.card-desc {
  font-family: var(--sf-font-body);
  font-weight: 500;
  font-size: 16px;
  line-height: 1.5;
  color: var(--sf-teal-muted);
  flex-grow: 1;
}

.card-btn {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 12px 24px;
  border-radius: 100px;
  border: 1px solid var(--sf-teal-deep);
  background: transparent;
  color: var(--sf-teal-deep);
  font-family: var(--sf-font-secondary);
  font-weight: 700;
  font-size: 16px;
  transition: all 0.3s ease;
  margin-top: 16px;
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
    gap: 24px;
  }
  .courses-title {
    font-size: 32px;
  }
  .courses-subtitle {
    font-size: 16px;
  }
  .header-nav {
    display: none; /* Hide nav buttons on mobile */
  }
  .course-card {
    min-width: 244px;
  }
  .card-image-wrapper {
    height: 240px;
  }
  .card-title {
    font-size: 24px;
  }
  .card-desc {
    font-size: 14px;
  }
}
</style>
