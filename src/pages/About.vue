<template>
  <div>
    <!-- Hero Section -->
    <section class="pt-20 pb-16 bg-primary-900 text-white">
      <div class="container-custom">
        <div class="text-center max-w-3xl mx-auto reveal">
          <h1 class="text-4xl md:text-5xl font-bold mb-6">À Propos de Nous</h1>
          <p class="text-xl text-primary-100">Découvrez l'équipe LYNEGO PLOMBERIE, votre partenaire de confiance pour tous vos besoins en plomberie.</p>
        </div>
      </div>
    </section>
    
    <!-- Company Description -->
    <section class="py-16 bg-white">
      <div class="container-custom">
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
          <div class="reveal" v-motion-slide-visible-once-right>
            <h2 class="text-3xl font-bold mb-4">Notre Histoire</h2>
            <div class="w-24 h-1 bg-primary-500 mb-6"></div>
            
            <p class="text-gray-700 mb-4">
              LYNEGO PLOMBERIE a été fondée avec une mission simple : fournir des services de plomberie exceptionnels, disponibles à tout moment pour répondre aux besoins des clients.
            </p>
            
            <p class="text-gray-700 mb-4">
              Notre équipe de plombiers expérimentés s'engage à offrir un service de qualité supérieure avec une garantie de satisfaction totale.
            </p>
            
            <p class="text-gray-700 mb-4">
              Nous investissons constamment dans les dernières technologies et formations pour rester à la pointe de notre industrie.
            </p>
            
            <div class="bg-gray-100 p-6 rounded-lg mt-8">
              <div class="flex items-center mb-3">
                <Phone class="w-5 h-5 text-primary-600 mr-3" />
                <span class="font-semibold">Numéro : </span>
                <a href="tel:0778646262" class="ml-2 text-primary-600 hover:underline">0778646262</a>
              </div>
              
              <div class="flex items-center">
                <Clock class="w-5 h-5 text-primary-600 mr-3" />
                <span class="font-semibold">Disponibilité : </span>
                <span class="ml-2">Ouvert 24h/24 – 7j/7</span>
              </div>
            </div>
          </div>
          
          <div class="reveal">
            <img src="https://images.pexels.com/photos/8478671/pexels-photo-8478671.jpeg" 
                 alt="Équipe de plombiers professionnels" 
                 class="rounded-lg shadow-xl w-full h-auto object-cover" />
          </div>
        </div>
      </div>
    </section>
    
    <!-- Values Section -->
    <section class="py-16 bg-gray-50">
      <div class="container-custom">
        <div class="text-center mb-12 reveal">
          <h2 class="text-3xl font-bold mb-4">Nos Valeurs</h2>
          <div class="w-24 h-1 bg-primary-500 mx-auto mb-6"></div>
          <p class="text-lg text-gray-600 max-w-2xl mx-auto">
            Les principes qui guident chacune de nos interventions.
          </p>
        </div>
        
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
          <div v-for="(value, index) in values" :key="index" 
               class="bg-white p-6 rounded-lg shadow-md text-center reveal"
               :style="{ animationDelay: `${index * 0.1}s` }">
            <div class="bg-primary-100 p-4 rounded-full w-16 h-16 flex items-center justify-center mb-4 mx-auto">
              <component :is="value.icon" class="w-7 h-7 text-primary-600" />
            </div>
            <h3 class="text-xl font-semibold mb-3">{{ value.title }}</h3>
            <p class="text-gray-600">{{ value.description }}</p>
          </div>
        </div>
      </div>
    </section>
    
    <!-- Team Section -->
    <section class="py-16 bg-white">
      <div class="container-custom">
        <div class="text-center mb-12 reveal">
          <h2 class="text-3xl font-bold mb-4">Notre Équipe</h2>
          <div class="w-24 h-1 bg-primary-500 mx-auto mb-6"></div>
          <p class="text-lg text-gray-600 max-w-2xl mx-auto">
            Une équipe de professionnels qualifiés prêts à intervenir 24h/24 et 7j/7.
          </p>
        </div>
        
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 reveal">
          <div class="bg-white rounded-lg shadow-md overflow-hidden">
            <img src="https://images.pexels.com/photos/8550716/pexels-photo-8550716.jpeg" 
                 alt="Plombier professionnel" 
                 class="w-full h-64 object-cover" />
            <div class="p-6">
              <h3 class="text-xl font-semibold mb-2">Technicien en Chef</h3>
              <p class="text-gray-600">Spécialiste en débouchage et réparations d'urgence avec plus de 10 ans d'expérience.</p>
            </div>
          </div>
          
          <div class="bg-white rounded-lg shadow-md overflow-hidden">
            <img src="https://images.pexels.com/photos/8550715/pexels-photo-8550715.jpeg" 
                 alt="Équipe d'intervention" 
                 class="w-full h-64 object-cover" />
            <div class="p-6">
              <h3 class="text-xl font-semibold mb-2">Équipe d'Intervention</h3>
              <p class="text-gray-600">Notre équipe mobile est prête à intervenir rapidement pour tous types d'urgences.</p>
            </div>
          </div>
          
          <div class="bg-white rounded-lg shadow-md overflow-hidden">
            <img src="https://images.pexels.com/photos/8487934/pexels-photo-8487934.jpeg" 
                 alt="Expert en rénovation" 
                 class="w-full h-64 object-cover" />
            <div class="p-6">
              <h3 class="text-xl font-semibold mb-2">Expert en Rénovation</h3>
              <p class="text-gray-600">Spécialiste des rénovations de salles de bain et installations sanitaires complexes.</p>
            </div>
          </div>
        </div>
      </div>
    </section>
    
    <!-- CTA Section -->
    <section class="py-16 bg-primary-900 text-white">
      <div class="container-custom text-center reveal">
        <h2 class="text-3xl md:text-4xl font-bold mb-6">Prêt à faire appel à nos services ?</h2>
        <p class="text-xl mb-8 max-w-3xl mx-auto">
          Notre équipe est disponible 24h/24 et 7j/7 pour répondre à tous vos besoins en plomberie.
        </p>
        
        <div class="flex flex-col sm:flex-row justify-center gap-4">
          <a href="tel:0778646262" class="btn bg-accent-500 hover:bg-accent-600 text-white px-8 py-4 rounded-lg font-semibold inline-flex items-center justify-center">
            <Phone class="w-5 h-5 mr-2" />
            Appeler Maintenant
          </a>
          
          <router-link to="/contact" class="btn bg-white hover:bg-gray-100 text-primary-800 px-8 py-4 rounded-lg font-semibold inline-flex items-center justify-center">
            <MessageSquare class="w-5 h-5 mr-2" />
            Nous Contacter
          </router-link>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup lang="ts">
import { Phone, Clock, MessageSquare, Shield, Clock8, PenTool as Tool, ThumbsUp } from 'lucide-vue-next';

// Set document title
import { onMounted } from 'vue';
onMounted(() => {
  document.title = 'À Propos - LYNEGO PLOMBERIE';
});

const values = [
  {
    title: 'Fiabilité',
    description: 'Nous sommes là quand vous avez besoin de nous, 24h/24 et 7j/7.',
    icon: Clock8
  },
  {
    title: 'Qualité',
    description: 'Un travail soigné avec des matériaux de première qualité.',
    icon: ThumbsUp
  },
  {
    title: 'Expertise',
    description: 'Des plombiers formés et expérimentés pour chaque intervention.',
    icon: Tool
  },
  {
    title: 'Garantie',
    description: 'Tous nos travaux sont garantis pour votre tranquillité d\'esprit.',
    icon: Shield
  }
];
</script>