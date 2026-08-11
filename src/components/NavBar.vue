<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const isScrolled = ref(false)
const isMobileMenuOpen = ref(false)

const handleScroll = () => {
  isScrolled.value = window.scrollY > 50
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})

const toggleMenu = () => {
  isMobileMenuOpen.value = !isMobileMenuOpen.value
}
</script>

<template>
  <header :class="['navbar', { 'navbar--scrolled': isScrolled }]">
    <div class="navbar__container sf-container">
      
      <!-- Right Side: Logo -->
      <div class="navbar__logo">
        <a href="/">
          <img src="/icons/logo.svg" alt="Safia Tahar Logo" class="logo-img" />
        </a>
      </div>

      <!-- Center: Navigation Links (Desktop only) -->
      <nav class="navbar__nav">
        <ul class="navbar__menu">
          <li><a href="#home" class="navbar__link navbar__link--active">الرئيسية</a></li>
          <li><a href="#courses" class="navbar__link">الدورات</a></li>
          <li><a href="#consulting" class="navbar__link">الاستشارات</a></li>
          <li><a href="#events" class="navbar__link">ويبينار</a></li>
          <li><a href="#membership" class="navbar__link">عضوية النخبة</a></li>
          <li><a href="#about" class="navbar__link">عن صفية</a></li>
        </ul>
      </nav>

      <!-- Left Side: Actions -->
      <div class="navbar__actions">
        <a href="#login" class="navbar__login-link">سجل دخولك</a>
        
        <div class="navbar__icons">
          <button class="navbar__icon-btn" aria-label="Cart">
            <img src="/icons/cart.svg" alt="Cart" class="nav-icon" />
          </button>
          <button class="navbar__icon-btn" aria-label="Search">
            <img src="/icons/search.svg" alt="Search" class="nav-icon" />
          </button>
        </div>

        <button class="navbar__btn-menu-mobile" @click="toggleMenu" aria-label="Menu">
          <img src="/icons/menu.svg" alt="Menu" class="nav-icon" />
        </button>
      </div>

    </div>
  </header>
</template>

<style scoped>
.navbar {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  z-index: 100;
  transition: all 0.3s ease;
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
}

.navbar--scrolled {
  position: fixed;
  background-color: var(--sf-teal-deep);
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
  border-bottom: none;
}

.navbar__container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: 96px;
  padding: 0 80px;
}

.navbar__logo a {
  display: flex;
  align-items: center;
}

.logo-img {
  width: 90px;
  height: auto;
  filter: brightness(0) invert(1);
}

.navbar__nav {
  display: flex;
  align-items: center;
}

.navbar__menu {
  display: flex;
  list-style: none;
  margin: 0;
  padding: 0;
  gap: 48px;
}

.navbar__link {
  font-family: var(--sf-font-body);
  font-weight: 500;
  font-size: 18px;
  color: rgba(255, 255, 255, 0.8);
  transition: color 0.3s ease;
  position: relative;
  padding-bottom: 8px;
}

.navbar__link:hover, .navbar__link--active {
  color: #FFFFFF;
  font-weight: 700;
}

.navbar__link--active::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 2px;
  background-color: #FFFFFF;
}

.navbar__actions {
  display: flex;
  align-items: center;
  gap: 32px;
}

.navbar__login-link {
  font-family: var(--sf-font-body);
  font-weight: 500;
  font-size: 18px;
  color: #FFFFFF;
  transition: opacity 0.3s ease;
}

.navbar__login-link:hover {
  opacity: 0.8;
}

.navbar__icons {
  display: flex;
  align-items: center;
  gap: 24px;
}

.navbar__icon-btn {
  display: flex;
  align-items: center;
  justify-content: center;
  background: none;
  transition: opacity 0.3s ease;
  padding: 0;
}

.navbar__icon-btn:hover {
  opacity: 0.7;
}

.nav-icon {
  width: 24px;
  height: 24px;
  filter: brightness(0) invert(1);
}

.navbar__btn-menu-mobile {
  display: none;
  align-items: center;
  justify-content: center;
  background: none;
  padding: 0;
}

@media (max-width: 1024px) {
  .navbar__nav {
    display: none;
  }
  
  .navbar__btn-menu-mobile {
    display: flex;
  }

  .navbar__container {
    padding: 0 24px;
  }
}

@media (max-width: 768px) {
  .navbar__container {
    height: 72px;
  }
  .navbar__icons, .navbar__login-link {
    display: none;
  }
  .logo-img {
    width: 64px;
  }
}
</style>
