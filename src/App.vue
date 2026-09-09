<script setup>
import SiteNav from './components/SiteNav.vue'
import HeroSection from './components/HeroSection.vue'
import WorkSection from './components/ProjectSection.vue'
import AboutSection from './components/AboutSection.vue'
import ContactSection from './components/ContactSection.vue'
import SiteFooter from './components/SiteFooter.vue'
</script>

<template>
  <div class="app-container">
    <SiteNav />
    <main>
      <HeroSection />
      <WorkSection />
      <AboutSection />
      <ContactSection />
    </main>
    <SiteFooter />
  </div>
</template>