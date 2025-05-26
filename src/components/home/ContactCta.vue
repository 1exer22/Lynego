<template>
  <section class="py-16 bg-primary-900 text-white">
    <div class="container-custom">
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
        <div class="reveal" v-motion-slide-visible-once-left>
          <h2 class="text-3xl md:text-4xl font-bold mb-4">Besoin d'un Plombier Urgence ?</h2>
          <div class="w-24 h-1 bg-accent-500 mb-6"></div>
          
          <p class="text-xl mb-8">
            Notre équipe de plombiers professionnels est disponible 24h/24 et 7j/7 pour répondre à toutes vos urgences.
          </p>
          
          <div class="bg-primary-800 p-6 rounded-lg mb-8">
            <div class="flex items-center mb-4">
              <Phone class="w-6 h-6 text-accent-500 mr-3" />
              <span class="font-semibold text-lg">Appelez-nous : </span>
              <a href="tel:0778646262" class="ml-2 text-accent-400 hover:text-accent-300 text-lg font-bold">
                0778646262
              </a>
            </div>
            
            <div class="flex items-center">
              <Clock class="w-6 h-6 text-accent-500 mr-3" />
              <span class="font-semibold text-lg">Disponibilité : </span>
              <span class="ml-2 text-lg">Ouvert 24h/24 – 7j/7</span>
            </div>
          </div>
          
          <router-link to="/contact" class="btn bg-accent-500 hover:bg-accent-600 text-white text-lg px-8 py-4 rounded-lg font-semibold inline-flex items-center">
            <MessageSquare class="w-5 h-5 mr-2" />
            Contactez-nous
          </router-link>
        </div>
        
        <div class="reveal">
          <div class="bg-white text-gray-800 p-8 rounded-lg shadow-lg">
            <h3 class="text-2xl font-bold mb-6 text-primary-800">Formulaire de Contact Rapide</h3>
            
            <form @submit.prevent="submitForm" class="space-y-4">
              <div>
                <label for="name" class="block text-sm font-medium text-gray-700 mb-1">Nom</label>
                <input 
                  type="text" 
                  id="name" 
                  v-model="form.name" 
                  class="w-full px-4 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-primary-500"
                  placeholder="Votre nom"
                  required
                >
              </div>
              
              <div>
                <label for="phone" class="block text-sm font-medium text-gray-700 mb-1">Téléphone</label>
                <input 
                  type="tel" 
                  id="phone" 
                  v-model="form.phone" 
                  class="w-full px-4 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-primary-500"
                  placeholder="Votre numéro de téléphone"
                  required
                >
              </div>
              
              <div>
                <label for="message" class="block text-sm font-medium text-gray-700 mb-1">Message</label>
                <textarea 
                  id="message" 
                  v-model="form.message" 
                  rows="4" 
                  class="w-full px-4 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-primary-500"
                  placeholder="Décrivez votre problème de plomberie"
                  required
                ></textarea>
              </div>
              
              <button 
                type="submit" 
                class="w-full bg-primary-600 hover:bg-primary-700 text-white font-bold py-3 px-4 rounded-md transition-colors duration-300"
              >
                Envoyer ma demande
              </button>
            </form>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import { Phone, Clock, MessageSquare } from 'lucide-vue-next';

const form = ref({
  name: '',
  phone: '',
  message: ''
});

const submitForm = () => {
  // In a real application, you would send the form data to a server
  alert(`Merci ${form.value.name}! Nous vous contacterons très rapidement au ${form.value.phone}.`);
  // Reset form
  form.value = {
    name: '',
    phone: '',
    message: ''
  };
};
</script>