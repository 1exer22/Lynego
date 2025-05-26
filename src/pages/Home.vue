<template>
  <div>
    <HeroSection />
    <ServicesPreview />
    <AboutPreview />
    <GalleryPreview />
    <ReviewsPreview />
    <ContactCta />
  </div>
</template>

<script setup lang="ts">
import HeroSection from '../components/home/HeroSection.vue';
import ServicesPreview from '../components/home/ServicesPreview.vue';
import AboutPreview from '../components/home/AboutPreview.vue';
import GalleryPreview from '../components/home/GalleryPreview.vue';
import ReviewsPreview from '../components/home/ReviewsPreview.vue';
import ContactCta from '../components/home/ContactCta.vue';

// Set document title
import { onMounted } from 'vue';
onMounted(() => {
  document.title = 'LYNEGO PLOMBERIE - Services de plomberie 24h/24 et 7j/7';
});
</script>