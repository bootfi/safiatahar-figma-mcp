<script setup>
const stories = [
  {
    id: 1,
    name: 'خلود',
    quote: 'حبيت اشكرك على انك انت صفية، فعلا وجودي معك في المعجزات والاستقبال غير كل شي مع انني حضرت كورسات دكاترة ثانيين ، لكن سبحان الله انتي غير.',
    avatar: '/images/avatar-kholoud.png'
  },
  {
    id: 2,
    name: 'أحمد',
    quote: 'بصراحة، تجربتي مع صفية طاهر كانت نقطة تحول في حياتي. أسلوبها واضح، عملي، ويخليك تشوف الأمور من زاوية مختلفة. قدرت أغير كثير من القناعات التي كانت تعيقني، وأصبحت أكثر ثقة وتركيزًا في أهدافي.',
    avatar: '/images/avatar-arwa.png' /* Fallback since Ahmad avatar not found */
  },
  {
    id: 3,
    name: 'أروى',
    quote: 'مدام صفية تعرفي انو بعد كورس المعجزات قدرت احقق اول 1000 دولار وزيادة فقط من الجلسات الفردية. صارلي سنة وانا بشتغل ككوتش ومرافقة لمرضى السرطان ما وصلت للمبلغ والجميل تدفق رهيب الحمد لله.',
    avatar: '/images/avatar-arwa.png'
  }
]
</script>

<template>
  <section class="stories-section">
    <div class="stories-container sf-container">
      
      <div class="stories-header">
        <h2 class="stories-title">قصص من عاشوا التحوُّل</h2>
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
                <img src="/icons/quote.svg" alt="Quote" />
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
  padding: 80px 0;
  background-color: var(--sf-bg-primary);
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
  gap: 8px;
}

.stories-title {
  font-family: var(--sf-font-secondary);
  font-weight: 700;
  font-size: 48px;
  color: var(--sf-gold);
}

.stories-subtitle {
  font-family: var(--sf-font-body);
  font-weight: 400;
  font-size: 20px;
  color: var(--sf-teal-deep);
}

.stories-content {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 48px;
}

.stories-list {
  display: flex;
  gap: 24px;
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
  background-color: var(--sf-bg-ivory);
  border-radius: 24px;
  padding: 64px 24px 24px;
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  gap: 16px;
  height: 100%;
  min-height: 250px;
}

.story-quote-icon {
  width: 24px;
  height: 24px;
}

.story-text {
  font-family: var(--sf-font-body);
  font-weight: 500;
  font-size: 16px;
  line-height: 1.5;
  color: var(--sf-teal-deep); /* or teal-muted */
  flex-grow: 1;
}

.story-name {
  font-family: var(--sf-font-body);
  font-weight: 700;
  font-size: 20px;
  color: var(--sf-teal-deep);
}

.stories-nav {
  display: flex;
  align-items: center;
  gap: 8px;
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
    font-size: 32px;
  }
  .stories-subtitle {
    font-size: 16px;
  }
  .story-card {
    width: 329px;
  }
}
</style>
