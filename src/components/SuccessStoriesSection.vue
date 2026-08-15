<script setup>
import { getAssetUrl } from '../utils/assets.js'

const stories = [
  {
    id: 1,
    name: 'خلود',
    quote: 'حبيت اشكرك على انك انت صفية، فعلا وجودي معك في المعجزات والاستقبال غير كل شي مع انني حضرت كورسات دكاترة ثانيين ، لكن سبحان الله انتي غير.',
    avatar: getAssetUrl('/images/avatar-kholoud.png')
  },
  {
    id: 2,
    name: 'أحمد',
    quote: 'بصراحة، تجربتي مع صفية طاهر كانت نقطة تحول في حياتي. أسلوبها واضح، عملي، ويخليك تشوف الأمور من زاوية مختلفة. قدرت أغير كثير من القناعات التي كانت تعيقني، وأصبحت أكثر ثقة وتركيزًا في أهدافي.',
    avatar: getAssetUrl('/images/avatar-arwa.png')
  },
  {
    id: 3,
    name: 'أروى',
    quote: 'مدام صفية تعرفي انو بعد كورس المعجزات قدرت احقق اول 1000 دولار وزيادة فقط من الجلسات الفردية. صارلي سنة وانا بشتغل ككوتش ومرافقة لمرضى السرطان ما وصلت للمبلغ والجميل تدفق رهيب الحمد لله.',
    avatar: getAssetUrl('/images/avatar-arwa.png')
  }
]
</script>

<template>
  <section class="stories-section">
    <div class="stories-container sf-container">
      
      <div class="stories-header">
        <h2 class="stories-title">قصص من عاشوا التحوُّل</h2>
        <p class="stories-subtitle">كيف أصبحت 'صفية' رفيقة دربهم نحو الوعي؟</p>
      </div>

      <div class="stories-content">
        <div class="stories-list">
          <div class="story-card" v-for="story in stories" :key="story.id">
            <div class="story-avatar-wrapper">
              <img :src="story.avatar" :alt="story.name" class="story-avatar" />
            </div>
            
            <div class="story-card-inner">
              <div class="story-quote-icon">
                <img :src="getAssetUrl('/icons/quote.svg')" alt="Quote" />
              </div>
              
              <p class="story-text">{{ story.quote }}</p>
              <h3 class="story-name">{{ story.name }}</h3>
            </div>
          </div>
        </div>

        <div class="stories-nav">
          <span class="nav-dot"></span>
          <span class="nav-dot"></span>
          <span class="nav-dot"></span>
          <span class="nav-dot nav-dot--active"></span>
        </div>
      </div>

    </div>
  </section>
</template>

<style scoped>
.stories-section {
  padding: var(--spacing-3xl) 0;          /* 80px 0 */
  background-color: var(--color-surface-main);
}

.stories-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 95px; /* Figma: 95px */
}

.stories-header {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  gap: var(--spacing-xs);                 /* 8px — Spacing-xs */
}

.stories-title {
  font-family: var(--font-family-primary); /* Noto Naskh Arabic */
  font-weight: var(--font-weight-bold);
  font-size: var(--font-size-xl);          /* 48px — Font-size-xl */
  color: var(--color-accent-500);
}

.stories-subtitle {
  font-family: var(--font-family-secondary); /* Tajawal */
  font-weight: var(--font-weight-regular);
  font-size: var(--font-size-body);          /* 20px — Font-size-body */
  color: var(--color-primary-500);
}

.stories-content {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: var(--spacing-xl);                 /* 48px — Spacing-xl */
}

.stories-list {
  display: flex;
  gap: var(--spacing-md);                 /* 24px — Spacing-md */
  justify-content: center;
  flex-wrap: wrap;
}

.story-card {
  position: relative;
  width: 411px;
  margin-top: 38px; /* For avatar overlap */
}

.story-avatar-wrapper {
  position: absolute;
  top: -38px;
  left: 50%;
  transform: translateX(-50%);
  width: 76px;
  height: 76px;
  border-radius: 50%;
  overflow: hidden;
  z-index: 2;
}

.story-avatar {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.story-card-inner {
  background-color: var(--color-surface-secondary);
  border-radius: var(--radius-mid);       /* 24px — Radius-mid */
  padding: var(--spacing-2xl) var(--spacing-md) var(--spacing-md); /* 64px 24px 24px */
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  gap: var(--spacing-sm);                 /* 16px — Spacing-sm */
  height: 100%;
  min-height: 250px;
}

.story-quote-icon {
  width: 24px;
  height: 24px;
}

.story-text {
  font-family: var(--font-family-secondary); /* Tajawal */
  font-weight: var(--font-weight-medium);
  font-size: var(--font-size-sm);            /* 16px — Font-size-sm */
  line-height: 1.5;
  color: var(--color-primary-500);
  flex-grow: 1;
}

.story-name {
  font-family: var(--font-family-secondary);
  font-weight: var(--font-weight-bold);
  font-size: var(--font-size-body);          /* 20px — Font-size-body */
  color: var(--color-primary-500);
}

.stories-nav {
  display: flex;
  align-items: center;
  gap: var(--spacing-xs);                 /* 8px — Spacing-xs */
}

.nav-dot {
  width: 12px;
  height: 12px;
  border-radius: 50%;
  background-color: var(--sf-gold-light);
}

.nav-dot--active {
  width: 17px;
  height: 17px;
  background-color: var(--sf-teal-deep);
}

@media (max-width: 1024px) {
  .stories-list {
    flex-direction: column;
    align-items: center;
  }
}

@media (max-width: 768px) {
  .stories-title {
    font-size: var(--font-size-lg);       /* 32px */
  }
  .stories-subtitle {
    font-size: var(--font-size-sm);       /* 16px */
  }
  .story-card {
    width: 329px;
  }
}
</style>
