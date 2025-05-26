<template>
  <section class="py-16 bg-gray-50">
    <div class="container-custom">
      <div class="text-center mb-12 reveal">
        <h2 class="text-3xl md:text-4xl font-bold mb-4">Nos Réalisations</h2>
        <div class="w-24 h-1 bg-primary-500 mx-auto mb-6"></div>
        <p class="text-lg text-gray-600 max-w-2xl mx-auto">
          Découvrez quelques-unes de nos réalisations récentes pour des clients satisfaits.
        </p>
      </div>
      
      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
        <div v-for="(image, index) in galleryImages.slice(0, 6)" :key="index" 
             class="reveal overflow-hidden rounded-lg shadow-md"
             :style="{ animationDelay: `${index * 0.1}s` }">
          <div class="relative group h-64">
            <img :src="image.url" :alt="image.alt" 
                 class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-110" />
            <div class="absolute inset-0 bg-primary-900/60 opacity-0 group-hover:opacity-100 flex items-center justify-center transition-opacity duration-300">
              <div class="text-white text-center p-4">
                <h3 class="text-xl font-semibold mb-2">{{ image.title }}</h3>
                <p>{{ image.description }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>
      
      <div class="text-center mt-12 reveal">
        <router-link to="/gallery" class="btn btn-primary">
          Voir toutes nos réalisations
          <ArrowRight class="w-5 h-5 ml-2" />
        </router-link>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ArrowRight } from 'lucide-vue-next';

const galleryImages = [
  {
    url: 'https://images.pexels.com/photos/6758773/pexels-photo-6758773.jpeg',
    alt: 'Rénovation complète salle de bain',
    title: 'Rénovation Salle de Bain',
    description: 'Transformation complète avec douche à l\'italienne'
  },
  {
    url: 'https://images.pexels.com/photos/6868286/pexels-photo-6868286.jpeg',
    alt: 'Installation sanitaire',
    title: 'Installation Sanitaire',
    description: 'Mise en place de nouveaux équipements'
  },
  {
    url: 'https://images.pexels.com/photos/4099358/pexels-photo-4099358.jpeg',
    alt: 'Réparation fuite',
    title: 'Réparation Fuite',
    description: 'Intervention d\'urgence pour stopper une fuite'
  },
  {
    url: 'https://images.pexels.com/photos/5691622/pexels-photo-5691622.jpeg',
    alt: 'Installation robinetterie',
    title: 'Installation Robinetterie',
    description: 'Installation de robinets modernes'
  },
  {
    url: 'https://images.pexels.com/photos/7937386/pexels-photo-7937386.jpeg',
    alt: 'Tuyauterie cuivre',
    title: 'Tuyauterie Cuivre',
    description: 'Installation professionnelle de tuyaux en cuivre'
  },
  {
    url: 'https://images.pexels.com/photos/6444256/pexels-photo-6444256.jpeg',
    alt: 'Débouchage canalisation',
    title: 'Débouchage',
    description: 'Intervention rapide sur canalisation bouchée'
  }
];
</script>