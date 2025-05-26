<template>
  <section class="py-16 bg-gray-50">
    <div class="container-custom">
      <div class="text-center mb-12 reveal">
        <h2 class="text-3xl md:text-4xl font-bold mb-4">Nos Services</h2>
        <div class="w-24 h-1 bg-primary-500 mx-auto mb-6"></div>
        <p class="text-lg text-gray-600 max-w-2xl mx-auto">
          Des solutions de plomberie professionnelles pour tous vos besoins, avec une garantie de qualité et de réactivité.
        </p>
      </div>
      
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div v-for="(service, index) in services" :key="index" 
             class="card card-hover p-6 reveal" 
             :style="{ animationDelay: `${index * 0.1}s` }">
          <div class="bg-primary-100 p-4 rounded-full w-16 h-16 flex items-center justify-center mb-6 transform transition-transform duration-500 hover:scale-110">
            <component :is="service.icon" class="w-8 h-8 text-primary-600" />
          </div>
          <h3 class="text-xl font-semibold mb-3">{{ service.title }}</h3>
          <p class="text-gray-600">{{ service.description }}</p>
        </div>
      </div>
      
      <div class="text-center mt-12 reveal">
        <router-link to="/services" class="btn btn-primary">
          Voir tous nos services
          <ArrowRight class="w-5 h-5 ml-2" />
        </router-link>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { Droplet, Bath, Search, Flame, Wrench, ArrowRight } from 'lucide-vue-next';

const services = [
  {
    title: 'Débouchage urgent',
    description: 'Intervention rapide pour déboucher vos canalisations et évacuations.',
    icon: Droplet
  },
  {
    title: 'Rénovation de salle de bain',
    description: 'Transformation complète de votre salle de bain selon vos envies.',
    icon: Bath
  },
  {
    title: 'Recherche de fuites',
    description: 'Détection précise et non destructive de toutes les fuites d\'eau.',
    icon: Search
  },
  {
    title: 'Réparation de chauffe-eau',
    description: 'Dépannage et réparation de tous types de chauffe-eau et cumulus.',
    icon: Flame
  },
  {
    title: 'Installation sanitaire',
    description: 'Installation professionnelle de tous vos équipements sanitaires.',
    icon: Wrench
  },
  {
    title: 'Dépannage 24h/24',
    description: 'Service d\'urgence disponible jour et nuit pour tous vos problèmes de plomberie.',
    icon: Droplet
  }
];
</script>