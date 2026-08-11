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
      <div class="navbar__pill">
        
        <!-- Right Side (RTL): Actions -->
        <div class="navbar__actions">
          <button class="navbar__icon-btn" aria-label="Search">
            <img src="/icons/search.svg" alt="Search" class="nav-icon" />
          </button>
          <button class="navbar__icon-btn" aria-label="Cart">
            <img src="/icons/cart.svg" alt="Cart" class="nav-icon" />
          </button>
          <button class="navbar__login-btn">سجل دخولك</button>
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

        <!-- Left Side (RTL): Logo -->
        <div class="navbar__logo">
          <a href="/">
            <img src="/icons/logo.svg" alt="Safia Tahar Logo" class="logo-img" />
          </a>
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
}

.navbar--scrolled {
  position: fixed;
  background-color: transparent;
}

.navbar--scrolled .navbar__pill {
  background-color: var(--sf-bg-primary);
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
}

.navbar--scrolled .logo-img {
  filter: none;
}

.navbar--scrolled .nav-icon {
  filter: none;
}

.navbar--scrolled .navbar__link {
  color: var(--sf-teal-deep);
}

.navbar--scrolled .navbar__link--active {
  color: var(--sf-teal-deep);
}

.navbar--scrolled .navbar__link--active::after {
  background-color: var(--sf-teal-deep);
}

.navbar--scrolled .navbar__login-btn {
  color: var(--sf-dark);
}

.navbar__container {
  display: flex;
  justify-content: center;
  padding: 0 80px;
  padding-top: 70px; /* Figma y:70 */
}

.navbar__pill {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 1280px; /* Figma: 1280px */
  max-width: 100%;
  height: 80px; /* Figma: 80px */
  padding: 16px 32px; /* Figma: 16px 32px */
  border-radius: 1000px; /* Figma: pill shape */
  background: transparent;
  transition: all 0.3s ease;
}

.navbar__logo a {
  display: flex;
  align-items: center;
}

.logo-img {
  width: 90px;
  height: auto;
  filter: brightness(0) invert(1);
  transition: filter 0.3s ease;
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
  transition: background-color 0.3s ease;
}

.navbar__actions {
  display: flex;
  align-items: center;
  gap: 8px; /* Figma: gap 8px between action items */
}

.navbar__login-btn {
  font-family: var(--sf-font-secondary); /* Figma: NOTO NASKH ARABIC */
  font-weight: 700;
  font-size: 16px; /* Figma: 16px */
  line-height: 20px;
  color: #F8F5EF;
  background: none;
  padding: 8px 16px;
  height: 40px;
  border-radius: 1000px;
  transition: opacity 0.3s ease;
}

.navbar__login-btn:hover {
  opacity: 0.8;
}

.navbar__icon-btn {
  width: 40px; /* Figma: 40x40 */
  height: 40px;
  border-radius: 1000px;
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
  width: 14px; /* Figma: 14x14 */
  height: 14px;
  filter: brightness(0) invert(1);
  transition: filter 0.3s ease;
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
    padding-top: 34px; /* Mobile Figma AppBar y:34 */
  }

  .navbar__pill {
    width: 100%;
    height: 56px;
    padding: 8px 16px;
  }
}

@media (max-width: 768px) {
  .navbar__pill {
    height: 56px;
  }
  .navbar__actions {
    gap: 4px;
  }
  .navbar__login-btn {
    display: none;
  }
  .logo-img {
    width: 64px;
  }
}
</style>
