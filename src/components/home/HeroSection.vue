<template>
  <section class="relative min-h-screen bg-primary-900 flex items-center overflow-hidden">
    <!-- Background Image with Overlay -->
    <div class="absolute inset-0 bg-cover bg-center" 
         style="background-image: url('https://images.pexels.com/photos/6579568/pexels-photo-6579568.jpeg');">
      <div class="absolute inset-0 bg-primary-900/70"></div>
    </div>
    
    <!-- Animated Wave SVG Background -->
    <div class="absolute bottom-0 left-0 w-full overflow-hidden">
      <svg class="relative block w-full h-[100px]" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 120" preserveAspectRatio="none">
        <path d="M321.39,56.44c58-10.79,114.16-30.13,172-41.86,82.39-16.72,168.19-17.73,250.45-.39C823.78,31,906.67,72,985.66,92.83c70.05,18.48,146.53,26.09,214.34,3V0H0V27.35A600.21,600.21,0,0,0,321.39,56.44Z" 
              class="fill-white"></path>
      </svg>
    </div>
    
    <div class="container-custom relative z-10 text-white">
      <div class="max-w-2xl" v-motion-slide-visible-once-bottom>
        <h1 class="text-4xl md:text-5xl lg:text-6xl font-bold mb-2 text-reveal">
          <span class="text-reveal" style="animation-delay: 0.1s">LYNEGO PLOMBERIE</span>
        </h1>
        
        <div class="flex items-center mb-6 text-reveal" style="animation-delay: 0.3s">
          <div class="flex">
            <Star v-for="i in 5" :key="i" class="w-5 h-5 text-yellow-400" fill="currentColor" />
          </div>
          <span class="ml-2">(5.0 sur 5)</span>
        </div>
        
        <p class="text-xl md:text-2xl mb-8 text-reveal" style="animation-delay: 0.5s">
          Disponible 24h/24 - 7j/7, intervention rapide partout près de chez vous.
        </p>
        
        <div class="text-reveal" style="animation-delay: 0.7s">
          <a href="tel:0778646262" class="pulse-button btn btn-accent text-lg px-8 py-4 rounded-full font-semibold">
            <Phone class="w-5 h-5 mr-2" />
            Appeler Maintenant
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { Star, Phone } from 'lucide-vue-next';
</script>