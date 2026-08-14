<script setup>
</script>

<template>
  <footer class="footer-section">
    <!-- Big watermark logo -->
    <img src="/icons/logo-watermark.svg" alt="" class="footer-watermark" />
    
    <div class="footer-container sf-container">
      
      <!-- Top Section: Newsletter & Links -->
      <div class="footer-top">
        <!-- Newsletter Box -->
        <div class="newsletter-box">
          <div class="newsletter-icon-wrapper">
            <img src="/icons/mail.svg" alt="Mail" class="newsletter-icon" />
          </div>
          <div class="newsletter-text">
            <h4 class="newsletter-title">انضم إلى مجتمع صفية</h4>
            <p class="newsletter-desc">كن أول من يطّلع على أحدث الدورات، والتأملات، والإعلانات الحصرية</p>
          </div>
          <form class="newsletter-form" @submit.prevent>
            <div class="input-wrapper">
              <input type="email" placeholder="أدخل بريدك الإلكتروني" required />
            </div>
            <button type="submit" class="newsletter-btn">التسجيل</button>
          </form>
        </div>

        <!-- Links Columns -->
        <div class="footer-links">
          
          <div class="links-column">
            <h4 class="links-title">برامجنا</h4>
            <ul class="links-list">
              <li><a href="#">الدورات</a></li>
              <li><a href="#">الاستشارات</a></li>
              <li><a href="#">المقالات</a></li>
              <li><a href="#">عضوية النخبة</a></li>
              <li><a href="#">البودكاست</a></li>
            </ul>
          </div>

          <div class="links-column">
            <h4 class="links-title">معلومات</h4>
            <ul class="links-list">
              <li><a href="#">عن صفية</a></li>
              <li><a href="#">الأسئلة الشائعة</a></li>
              <li><a href="#">الشروط والسياسات</a></li>
            </ul>
          </div>
          
          <div class="links-column">
            <h4 class="links-title">تواصل</h4>
            <ul class="links-list contact-list">
              <li>
                <img src="/icons/mail.svg" alt="" class="contact-icon" />
                <a href="mailto:contact@safiatahar.com" dir="ltr">contact@safiatahar.com</a>
              </li>
              <li>
                <img src="/icons/whatsapp.svg" alt="" class="contact-icon" />
                <a href="tel:+971567693377" dir="ltr">+971567693377</a>
              </li>
              <li>
                <img src="/icons/location.svg" alt="" class="contact-icon" />
                <span>دبي، الإمارات</span>
              </li>
            </ul>
          </div>

        </div>
      </div>

      <!-- Divider line -->
      <div class="footer-divider"></div>

      <!-- Bottom Section: Socials & Copyright -->
      <div class="footer-bottom">
        <div class="social-links">
          <a href="#" class="social-link" aria-label="Facebook"><img src="/icons/facebook.svg" alt="" /></a>
          <a href="#" class="social-link" aria-label="Instagram"><img src="/icons/instagram.svg" alt="" /></a>
          <a href="#" class="social-link" aria-label="YouTube"><img src="/icons/youtube.svg" alt="" /></a>
          <a href="#" class="social-link" aria-label="TikTok"><img src="/icons/tiktok.svg" alt="" /></a>
        </div>
        
        <p class="copyright">© 2026 صفية طاهر | جميع الحقوق محفوظة</p>
      </div>

    </div>
  </footer>
</template>

<style scoped>
.footer-section {
  position: relative;
  background: var(--sf-gradient-teal-footer);
  padding: 0; /* Padding on container */
  overflow: hidden;
}

.footer-watermark {
  position: absolute;
  top: -24px; /* Figma: y:-24 */
  left: -60px; /* Figma: x:-60 */
  width: 595px;
  height: 464px;
  opacity: 0.08;
  pointer-events: none;
  z-index: 1;
}

.footer-container {
  position: relative;
  z-index: 2;
  display: flex;
  flex-direction: column;
  gap: var(--spacing-sm);                /* 16px — Spacing-sm */
  padding: var(--spacing-xl) var(--spacing-3xl); /* 48px 80px */
}

.footer-top {
  display: flex;
  justify-content: space-between;
  gap: var(--spacing-2xl);              /* 64px — Spacing-2xl */
}

/* Newsletter Box */
.newsletter-box {
  background-color: var(--color-surface-secondary);
  border-radius: var(--radius-mid);      /* 24px — Radius-mid */
  padding: var(--spacing-lg);            /* 32px — Spacing-lg */
  display: flex;
  flex-direction: column;
  gap: var(--spacing-md);                /* 24px — Spacing-md */
  max-width: 420px;
}

.newsletter-icon-wrapper {
  width: var(--spacing-2xl);             /* 64px — Spacing-2xl */
  height: var(--spacing-2xl);
  border-radius: var(--radius-mid-mobile); /* 16px — Radius-mid-mobile */
  background-color: rgba(9, 59, 51, 0.05);
  display: flex;
  align-items: center;
  justify-content: center;
}

.newsletter-icon {
  width: 32px;
  height: 32px;
  filter: brightness(0) invert(14%) sepia(26%) saturate(1637%) hue-rotate(123deg) brightness(96%) contrast(98%); /* Approximation for sf-teal-deep */
}

.newsletter-text {
  display: flex;
  flex-direction: column;
  gap: var(--spacing-xs);                /* 8px — Spacing-xs */
}

.newsletter-title {
  font-family: var(--font-family-primary);  /* Noto Naskh Arabic */
  font-weight: var(--font-weight-bold);
  font-size: var(--font-size-base);         /* 24px — Font-size-base */
  color: var(--color-primary-500);
}

.newsletter-desc {
  font-family: var(--font-family-secondary);  /* Tajawal */
  font-weight: var(--font-weight-regular);
  font-size: var(--font-size-sm);            /* 16px — Font-size-sm */
  line-height: 1.5;
  color: var(--color-primary-400);
}

.newsletter-form {
  display: flex;
  gap: var(--spacing-xs);               /* 8px — Spacing-xs */
}

.input-wrapper {
  flex: 1;
  border-radius: var(--radius-full);    /* 1000px — Radius-full */
  background-color: var(--color-surface-secondary);
  border: 1px solid rgba(0,0,0,0.1);
  overflow: hidden;
}

.newsletter-form input {
  width: 100%;
  height: var(--spacing-xl);            /* 48px — Spacing-xl */
  padding: 0 var(--spacing-sm);         /* 0 16px */
  border: none;
  background: transparent;
  font-family: var(--font-family-secondary);
  font-size: var(--font-size-xs);       /* 12px (was 14px, closest token) */
  color: var(--color-primary-500);
  outline: none;
}

.newsletter-btn {
  height: var(--spacing-xl);            /* 48px — Spacing-xl */
  padding: 0 var(--spacing-md);         /* 0 24px */
  border-radius: var(--radius-full);    /* 1000px — Radius-full */
  background-color: var(--sf-accent-pink);
  color: var(--color-primary-500);
  font-family: var(--font-family-primary);
  font-weight: var(--font-weight-bold);
  font-size: var(--font-size-sm);       /* 16px — Font-size-sm */
  transition: opacity 0.3s ease;
}

.newsletter-btn:hover {
  opacity: 0.9;
}

/* Links Columns */
.footer-links {
  display: flex;
  gap: var(--spacing-xl);               /* 48px — Spacing-xl */
  flex: 1;
  justify-content: flex-end;
}

.links-column {
  display: flex;
  flex-direction: column;
  gap: var(--spacing-md);               /* 24px — Spacing-md */
}

.links-title {
  font-family: var(--font-family-primary);  /* Noto Naskh Arabic */
  font-weight: var(--font-weight-bold);
  font-size: var(--font-size-base);         /* 24px — Font-size-base */
  color: #fff;
}

.links-list {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  flex-direction: column;
  gap: var(--spacing-sm);               /* 16px — Spacing-sm */
}

.links-list a, .links-list span {
  font-family: var(--font-family-secondary); /* Tajawal */
  font-weight: var(--font-weight-regular);
  font-size: var(--font-size-sm);           /* 16px — Font-size-sm */
  color: rgba(255, 255, 255, 0.8);
  transition: color 0.3s ease;
}

.links-list a:hover {
  color: #fff;
}

.contact-list li {
  display: flex;
  align-items: center;
  gap: 12px; /* No exact token for 12px */
}

.contact-icon {
  width: 20px;
  height: 20px;
  filter: brightness(0) invert(1);
}

.footer-divider {
  width: 100%;
  height: 0;
  border: none;
  border-top: 0.5px solid #F8F5ED; /* Figma: 0.5px #F8F5ED */
}

.footer-bottom {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: var(--spacing-md);               /* 24px — Spacing-md */
}

.social-links {
  display: flex;
  gap: var(--spacing-md);               /* 24px — Spacing-md */
}

.social-link {
  width: 32px; /* Figma: 32x32 */
  height: 32px;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: opacity 0.3s ease;
}

.social-link:hover {
  opacity: 0.7;
}

.social-link img {
  width: 32px;
  height: 32px;
  filter: brightness(0) invert(1);
}

.copyright {
  font-family: var(--font-family-secondary);
  font-weight: var(--font-weight-medium);
  font-size: var(--font-size-sm);       /* 16px — Font-size-sm */
  color: var(--color-white-400);
}

@media (max-width: 1024px) {
  .footer-top {
    flex-direction: column;
    align-items: center;
  }
  .newsletter-box {
    width: 100%;
    max-width: 100%;
  }
  .footer-links {
    width: 100%;
    justify-content: space-between;
    gap: 40px;
  }
}

@media (max-width: 768px) {
  .footer-section {
    padding: var(--spacing-xl) 0 var(--spacing-lg); /* 48px 0 32px */
  }
  .footer-container {
    padding: var(--spacing-xl) var(--spacing-md); /* 48px 24px */
    gap: var(--spacing-md);                        /* 24px */
  }
  .newsletter-box {
    padding: var(--spacing-md);                    /* 24px */
  }
  .newsletter-form {
    flex-direction: column;
  }
  .footer-links {
    flex-direction: column;
  }
  .links-column {
    align-items: center;
    text-align: center;
  }
  .contact-list li {
    justify-content: center;
  }
  .footer-watermark {
    width: 484px;
    height: 378px;
    left: -100px;
    top: auto;
    bottom: 0;
  }
}
</style>
