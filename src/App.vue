<script setup>
import NavBar from './components/NavBar.vue'
import HeroSection from './components/HeroSection.vue'
import AboutSection from './components/AboutSection.vue'
import PressSection from './components/PressSection.vue'
import TestimonialsVoiceSection from './components/TestimonialsVoiceSection.vue'
import CoursesSection from './components/CoursesSection.vue'
import EventsSection from './components/EventsSection.vue'
import SuccessStoriesSection from './components/SuccessStoriesSection.vue'
import AudioLibrarySection from './components/AudioLibrarySection.vue'
import PodcastSection from './components/PodcastSection.vue'
import PrivateConsultingSection from './components/PrivateConsultingSection.vue'
import EliteMembershipSection from './components/EliteMembershipSection.vue'
import CTABannerSection from './components/CTABannerSection.vue'
import FooterSection from './components/FooterSection.vue'
import FloatingActionButton from './components/FloatingActionButton.vue'
</script>

<template>
  <div class="sf-app-wrapper">
    <NavBar />
    <main>
      <HeroSection />
      <AboutSection />
      <PressSection />
      <TestimonialsVoiceSection />
      <CoursesSection />
      <EventsSection />
      <SuccessStoriesSection />
      <AudioLibrarySection />
      <PodcastSection />
      <PrivateConsultingSection />
      <EliteMembershipSection />
      <CTABannerSection />
      <FooterSection />
      <FloatingActionButton />
    </main>
  </div>
</template>

<style scoped>
.sf-app-wrapper {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}
</style>
