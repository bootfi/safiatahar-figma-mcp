<script setup>
</script>

<template>
  <section class="podcast-section">
    
    <div class="podcast-bg-text">PODCAST</div>
    <div class="podcast-author">صفية طاهر</div>

    <div class="podcast-container sf-container">
      <div class="podcast-content-wrapper">
        
        <div class="podcast-text-content">
          <p class="podcast-desc">
            حين امتزج التفرد مع التجربة و الترددات العالية خلق بودكاست "صفية طاهر"
            <br>
            رحلة تأخذك في قصص حقيقية تلامس اعماق روحك و توقظ صوتك الحقيقي لتجد طريقك في العالم.
          </p>

          <div class="podcast-cta">
            <p class="cta-title">تابع البودكاست على</p>
            <div class="cta-buttons">
              <button class="social-btn">
                <img src="/icons/youtube.svg" alt="YouTube" class="social-icon" />
                Youtube
              </button>
              <button class="social-btn">
                <img src="/icons/spotify.svg" alt="Spotify" class="social-icon" />
                Spotify
              </button>
            </div>
          </div>
        </div>

        <div class="podcast-image-wrapper">
          <img src="/images/podcast-cover-2cc170.png" alt="Safia Podcast" class="podcast-image" />
        </div>

      </div>
    </div>
  </section>
</template>

<style scoped>
.podcast-section {
  position: relative;
  background-color: var(--sf-bg-ivory); /* Actually in design it's a solid #F8F5EF or similar */
  padding: 160px 0 80px;
  overflow: hidden;
  margin-top: 100px;
}

.podcast-bg-text {
  position: absolute;
  bottom: 0;
  left: 20px;
  font-family: var(--sf-font-english);
  font-weight: 400;
  font-size: 200px;
  line-height: 1;
  color: var(--sf-ivory-alt);
  opacity: 0.1; /* Figma: 0.1 */
  pointer-events: none;
  z-index: 1;
  white-space: nowrap;
}

.podcast-author {
  position: absolute;
  top: 40px;
  right: 120px;
  font-family: var(--sf-font-secondary);
  font-weight: 700;
  font-size: 32px;
  color: var(--sf-gold);
  z-index: 2;
}

.podcast-container {
  position: relative;
  z-index: 3;
}

.podcast-content-wrapper {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 var(--spacing-3xl);           /* 0 80px */
}

.podcast-text-content {
  width: 50%;
  display: flex;
  flex-direction: column;
  gap: var(--spacing-xl);                  /* 48px — Spacing-xl */
}

.podcast-desc {
  font-family: var(--font-family-secondary); /* Tajawal */
  font-weight: var(--font-weight-medium);
  font-size: var(--font-size-base);          /* 24px — Font-size-base */
  line-height: 1.8;
  color: var(--color-primary-500);
}

.podcast-cta {
  display: flex;
  flex-direction: column;
  gap: var(--spacing-sm);                  /* 16px — Spacing-sm */
}

.cta-title {
  font-family: var(--font-family-secondary);
  font-weight: var(--font-weight-medium);
  font-size: var(--font-size-base);        /* 24px — Font-size-base */
  color: var(--color-primary-500);
}

.cta-buttons {
  display: flex;
  gap: var(--spacing-sm);                  /* 16px — Spacing-sm */
}

.social-btn {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: var(--spacing-xs);                  /* 8px — Spacing-xs */
  padding: 12px var(--spacing-md);         /* 12px 24px */
  border-radius: var(--radius-full);       /* 1000px — Radius-full */
  border: 1px solid var(--color-primary-500);
  background-color: transparent;
  color: var(--color-primary-500);
  font-family: var(--font-family-primary);
  font-weight: var(--font-weight-bold);
  font-size: var(--font-size-sm);          /* 16px — Font-size-sm */
  transition: all 0.3s ease;
}

.social-btn:hover {
  background-color: var(--sf-teal-deep);
  color: #fff;
}

.social-btn:hover .social-icon {
  filter: brightness(0) invert(1);
}

.social-icon {
  width: 24px;
  height: 24px;
  transition: filter 0.3s ease;
}

.podcast-image-wrapper {
  width: 50%;
  display: flex;
  justify-content: center;
  position: relative;
}

.podcast-image {
  max-width: 360px;
  border-radius: var(--radius-mid);        /* 24px — Radius-mid */
  box-shadow: 0 20px 40px rgba(0,0,0,0.1);
  transform: translateY(-80px);
}

@media (max-width: 1024px) {
  .podcast-content-wrapper {
    flex-direction: column;
    padding: 0 var(--spacing-md);          /* 0 24px */
    gap: var(--spacing-2xl);               /* 64px */
  }
  .podcast-text-content, .podcast-image-wrapper {
    width: 100%;
  }
  .podcast-author {
    right: 50%;
    transform: translateX(50%);
  }
  .podcast-image {
    transform: translateY(0);
  }
  .podcast-bg-text {
    font-size: 100px;
  }
}

@media (max-width: 768px) {
  .podcast-section {
    padding: 100px 0 var(--spacing-xl);    /* 100px 0 48px */
    margin-top: var(--spacing-xl);         /* 48px */
  }
  .podcast-desc {
    font-size: var(--font-size-sm);        /* 16px */
    text-align: center;
  }
  .podcast-cta {
    align-items: center;
  }
  .cta-title {
    font-size: var(--font-size-body);      /* 20px */
  }
  .podcast-image {
    max-width: 236px;
  }
}
</style>
