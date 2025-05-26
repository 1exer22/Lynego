<template>
  <section class="py-16 bg-white">
    <div class="container-custom">
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
        <div class="reveal">
          <img src="https://images.pexels.com/photos/8486972/pexels-photo-8486972.jpeg" 
               alt="Équipe de plombiers professionnels" 
               class="rounded-lg shadow-xl w-full h-auto object-cover max-h-[500px]" />
        </div>
        
        <div class="reveal" v-motion-slide-visible-once-right>
          <h2 class="text-3xl md:text-4xl font-bold mb-4">À Propos de Nous</h2>
          <div class="w-24 h-1 bg-primary-500 mb-6"></div>
          
          <p class="text-gray-600 mb-6">
            LYNEGO PLOMBERIE est votre partenaire de confiance pour tous vos travaux de plomberie.
            Notre équipe de professionnels qualifiés intervient rapidement pour résoudre tous vos problèmes.
          </p>
          
          <div class="bg-gray-100 p-6 rounded-lg mb-6">
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
          
          <router-link to="/about" class="btn btn-primary">
            En savoir plus
            <ArrowRight class="w-5 h-5 ml-2" />
          </router-link>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { Phone, Clock, ArrowRight } from 'lucide-vue-next';
</script>