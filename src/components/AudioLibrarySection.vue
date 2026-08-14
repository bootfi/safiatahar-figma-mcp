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
  padding: var(--spacing-3xl) 0;           /* 80px 0 */
  background-color: var(--color-surface-main);
}

.audio-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 95px; /* Figma: 95px */
}

.audio-header {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  gap: var(--spacing-xs);                  /* 8px — Spacing-xs */
}

.audio-title {
  font-family: var(--font-family-primary); /* Noto Naskh Arabic */
  font-weight: var(--font-weight-bold);
  font-size: var(--font-size-xl);          /* 48px — Font-size-xl */
  color: var(--color-accent-500);
}

.audio-subtitle {
  font-family: var(--font-family-secondary); /* Tajawal */
  font-weight: var(--font-weight-regular);
  font-size: var(--font-size-body);          /* 20px — Font-size-body */
  color: var(--color-primary-500);
}

.audio-list {
  display: flex;
  gap: var(--spacing-md);                  /* 24px — Spacing-md */
  width: 100%;
  justify-content: center;
}

.audio-card {
  position: relative;
  flex: 1;
  max-width: 411px;
  height: 470px;
  border-radius: var(--radius-mid);        /* 24px — Radius-mid */
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
  background: linear-gradient(180deg, rgba(0,0,0,0) 0%, rgba(0,0,0,0.5) 100%);
  z-index: 1;
}

.audio-card-content {
  position: relative;
  z-index: 2;
  padding: var(--spacing-xl) var(--spacing-lg); /* 48px 32px */
  display: flex;
  flex-direction: column;
  gap: var(--spacing-xs);                       /* 8px — Spacing-xs */
}

.card-title {
  font-family: var(--font-family-primary); /* Noto Naskh Arabic */
  font-weight: var(--font-weight-bold);
  font-size: var(--font-size-lg);          /* 32px — Font-size-lg */
  color: #fff;
}

.card-desc {
  font-family: var(--font-family-secondary); /* Tajawal */
  font-weight: var(--font-weight-regular);
  font-size: var(--font-size-sm);            /* 16px — Font-size-sm */
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
    padding: var(--spacing-xl) var(--spacing-md); /* 48px 24px */
  }
  .audio-title {
    font-size: var(--font-size-lg);              /* 32px */
  }
  .audio-subtitle {
    font-size: var(--font-size-sm);              /* 16px */
  }
  .audio-list {
    flex-direction: column;
    align-items: center;
    gap: var(--spacing-sm);                      /* 16px */
  }
  .audio-card {
    width: 100%;
    height: 202px;
  }
  .audio-card-content {
    padding: var(--spacing-md) var(--spacing-sm); /* 24px 16px */
  }
  .card-title {
    font-size: var(--font-size-base);            /* 24px */
  }
  .card-desc {
    font-size: var(--font-size-xs);              /* 12px (was 14px) */
  }
}
</style>
