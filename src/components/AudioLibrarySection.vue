<script setup>
const audioItems = [
  {
    id: 1,
    title: 'الأمسيات التوضيحية',
    description: 'تنظيفات قوية لتطهير و تحرير اي شي عالق.',
    image: '/images/audio-evenings.png'
  },
  {
    id: 2,
    title: 'جلسات التأمل',
    description: 'حين يهدأ العقل يقود القلب فتتجلى الانوار و الفتوحات',
    image: '/images/audio-meditation.png'
  },
  {
    id: 3,
    title: 'سبليمنال',
    description: 'ترددات مع كلام غير ظاهر يخترق عقلك الباطن لتغيير اسرع.',
    image: '/images/audio-subliminal.png'
  }
]
</script>

<template>
  <section class="audio-section">
    <div class="audio-container sf-container">
      
      <div class="audio-header">
        <h2 class="audio-title">المكتبة الصوتية</h2>
        <p class="audio-subtitle">أصوات وترددات خاصة، ترفع الطاقة وتعيد التناغم بين الروح والجسد.</p>
      </div>

      <div class="audio-list">
        <div 
          class="audio-card" 
          v-for="item in audioItems" 
          :key="item.id"
          :style="{ backgroundImage: `url(${item.image})` }"
        >
          <div class="audio-card-overlay"></div>
          <div class="audio-card-content">
            <h3 class="card-title">{{ item.title }}</h3>
            <p class="card-desc">{{ item.description }}</p>
          </div>
        </div>
      </div>

    </div>
  </section>
</template>

<style scoped>
.audio-section {
  padding: 80px 0;
  background-color: var(--sf-bg-primary);
}

.audio-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 64px;
}

.audio-header {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  gap: 8px;
}

.audio-title {
  font-family: var(--sf-font-secondary);
  font-weight: 700;
  font-size: 48px;
  color: var(--sf-teal-deep);
}

.audio-subtitle {
  font-family: var(--sf-font-body);
  font-weight: 500;
  font-size: 24px;
  color: var(--sf-teal-deep);
}

.audio-list {
  display: flex;
  gap: 24px;
  width: 100%;
  justify-content: center;
}

.audio-card {
  position: relative;
  flex: 1;
  max-width: 411px;
  height: 470px;
  border-radius: 24px;
  overflow: hidden;
  background-size: cover;
  background-position: center;
  display: flex;
  align-items: flex-end;
}

.audio-card-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(180deg, rgba(0,0,0,0) 0%, rgba(0,0,0,0.8) 100%);
  z-index: 1;
}

.audio-card-content {
  position: relative;
  z-index: 2;
  padding: 32px 24px;
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.card-title {
  font-family: var(--sf-font-secondary);
  font-weight: 700;
  font-size: 32px;
  color: #fff;
}

.card-desc {
  font-family: var(--sf-font-body);
  font-weight: 400;
  font-size: 16px;
  line-height: 1.5;
  color: rgba(255, 255, 255, 0.8);
}

@media (max-width: 1024px) {
  .audio-list {
    flex-wrap: wrap;
  }
  .audio-card {
    min-width: 300px;
  }
}

@media (max-width: 768px) {
  .audio-section {
    padding: 48px 24px;
  }
  .audio-title {
    font-size: 32px;
  }
  .audio-subtitle {
    font-size: 16px;
  }
  .audio-list {
    flex-direction: column;
    align-items: center;
    gap: 16px;
  }
  .audio-card {
    width: 100%;
    height: 202px;
  }
  .audio-card-content {
    padding: 24px 16px;
  }
  .card-title {
    font-size: 24px;
  }
  .card-desc {
    font-size: 14px;
  }
}
</style>
