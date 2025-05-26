<template>
  <div class="flex flex-col min-h-screen">
    <Navbar />
    <main class="flex-grow">
      <router-view v-slot="{ Component }">
        <transition name="fade" mode="out-in">
          <component :is="Component" />
        </transition>
      </router-view>
    </main>
    <Footer />
  </div>
</template>

<script setup lang="ts">
import { onMounted, onUnmounted } from 'vue';
import Navbar from './components/layout/Navbar.vue';
import Footer from './components/layout/Footer.vue';

// Scroll reveal function
const checkScroll = () => {
  const reveals = document.querySelectorAll('.reveal');
  
  for (let i = 0; i < reveals.length; i++) {
    const windowHeight = window.innerHeight;
    const elementTop = reveals[i].getBoundingClientRect().top;
    const elementVisible = 150;
    
    if (elementTop < windowHeight - elementVisible) {
      reveals[i].classList.add("active");
    }
  }
};

onMounted(() => {
  window.addEventListener('scroll', checkScroll);
  checkScroll(); // Check on initial load
});

onUnmounted(() => {
  window.removeEventListener('scroll', checkScroll);
});
</script>

<style>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>