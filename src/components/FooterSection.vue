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
  padding: 64px 0 48px;
  overflow: hidden;
}

.footer-watermark {
  position: absolute;
  bottom: 0;
  left: -100px;
  width: 484px;
  height: 378px;
  opacity: 0.08;
  pointer-events: none;
  z-index: 1;
}

.footer-container {
  position: relative;
  z-index: 2;
  display: flex;
  flex-direction: column;
  gap: 64px;
  padding: 0 80px;
}

.footer-top {
  display: flex;
  justify-content: space-between;
  gap: 64px;
}

/* Newsletter Box */
.newsletter-box {
  background-color: var(--sf-bg-ivory);
  border-radius: 24px;
  padding: 32px;
  display: flex;
  flex-direction: column;
  gap: 24px;
  max-width: 420px;
}

.newsletter-icon-wrapper {
  width: 64px;
  height: 64px;
  border-radius: 16px;
  background-color: rgba(9, 59, 51, 0.05); /* very light teal */
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
  gap: 8px;
}

.newsletter-title {
  font-family: var(--sf-font-secondary);
  font-weight: 700;
  font-size: 24px;
  color: var(--sf-teal-deep);
}

.newsletter-desc {
  font-family: var(--sf-font-body);
  font-weight: 400;
  font-size: 16px;
  line-height: 1.5;
  color: var(--sf-teal-muted);
}

.newsletter-form {
  display: flex;
  gap: 8px;
}

.input-wrapper {
  flex: 1;
  border-radius: 100px;
  background-color: var(--sf-bg-ivory); /* Matches box, could be white */
  border: 1px solid rgba(0,0,0,0.1);
  overflow: hidden;
}

.newsletter-form input {
  width: 100%;
  height: 48px;
  padding: 0 16px;
  border: none;
  background: transparent;
  font-family: var(--sf-font-body);
  font-size: 14px;
  color: var(--sf-teal-deep);
  outline: none;
}

.newsletter-btn {
  height: 48px;
  padding: 0 24px;
  border-radius: 100px;
  background-color: var(--sf-accent-pink); /* Design says pink/peach button for newsletter */
  color: var(--sf-teal-deep);
  font-family: var(--sf-font-secondary);
  font-weight: 700;
  font-size: 16px;
  transition: opacity 0.3s ease;
}

.newsletter-btn:hover {
  opacity: 0.9;
}

/* Links Columns */
.footer-links {
  display: flex;
  gap: 80px;
  flex: 1;
  justify-content: flex-end;
}

.links-column {
  display: flex;
  flex-direction: column;
  gap: 24px;
}

.links-title {
  font-family: var(--sf-font-secondary);
  font-weight: 700;
  font-size: 24px;
  color: #fff;
}

.links-list {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.links-list a, .links-list span {
  font-family: var(--sf-font-body);
  font-weight: 400;
  font-size: 16px;
  color: rgba(255, 255, 255, 0.8);
  transition: color 0.3s ease;
}

.links-list a:hover {
  color: #fff;
}

.contact-list li {
  display: flex;
  align-items: center;
  gap: 12px;
}

.contact-icon {
  width: 20px;
  height: 20px;
  filter: brightness(0) invert(1);
}

.footer-divider {
  width: 100%;
  height: 1px;
  background-color: rgba(255, 255, 255, 0.2);
}

.footer-bottom {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 24px;
}

.social-links {
  display: flex;
  gap: 24px;
}

.social-link {
  width: 40px;
  height: 40px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 50%;
  background-color: rgba(255, 255, 255, 0.1);
  transition: background-color 0.3s ease;
}

.social-link:hover {
  background-color: rgba(255, 255, 255, 0.2);
}

.social-link img {
  width: 20px;
  height: 20px;
  filter: brightness(0) invert(1);
}

.copyright {
  font-family: var(--sf-font-body);
  font-weight: 400;
  font-size: 14px;
  color: rgba(255, 255, 255, 0.6);
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
    padding: 48px 0 32px;
  }
  .footer-container {
    padding: 0 24px;
    gap: 48px;
  }
  .newsletter-box {
    padding: 24px;
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
    width: 300px;
    height: 234px;
    left: -50px;
  }
}
</style>
