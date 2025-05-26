<template>
  <footer class="bg-gray-900 text-white pt-12 pb-6">
    <div class="container-custom">
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
        <!-- Company Info -->
        <div>
          <h3 class="text-xl font-bold mb-4">LYNEGO PLOMBERIE</h3>
          <p class="mb-4">Service de plomberie professionnel disponible 24h/24 et 7j/7.</p>
          <div class="flex items-center mb-2">
            <Phone class="w-5 h-5 mr-2" />
            <a href="tel:0778646262" class="hover:text-primary-300 transition-colors">0778646262</a>
          </div>
          <div class="flex items-center">
            <Clock class="w-5 h-5 mr-2" />
            <span>Ouvert 24h/24 – 7j/7</span>
          </div>
        </div>

        <!-- Quick Links -->
        <div>
          <h3 class="text-xl font-bold mb-4">Liens Rapides</h3>
          <ul class="space-y-2">
            <li v-for="item in navItems" :key="item.path">
              <router-link :to="item.path" class="hover:text-primary-300 transition-colors">
                {{ item.name }}
              </router-link>
            </li>
          </ul>
        </div>

        <!-- Services -->
        <div>
          <h3 class="text-xl font-bold mb-4">Nos Services</h3>
          <ul class="space-y-2">
            <li v-for="service in services" :key="service">
              <router-link to="/services" class="hover:text-primary-300 transition-colors">
                {{ service }}
              </router-link>
            </li>
          </ul>
        </div>

        <!-- Contact -->
        <div>
          <h3 class="text-xl font-bold mb-4">Contact Urgence</h3>
          <a href="tel:0778646262" class="btn bg-accent-500 hover:bg-accent-600 text-white px-6 py-3 rounded-full inline-flex items-center mb-4">
            <Phone class="w-5 h-5 mr-2" />
            <span>Appel d'urgence</span>
          </a>
          <p>Pour toute urgence de plomberie, n'hésitez pas à nous contacter immédiatement.</p>
        </div>
      </div>

      <div class="border-t border-gray-700 mt-8 pt-6">
        <div class="flex flex-col md:flex-row justify-between items-center">
          <p>&copy; {{ new Date().getFullYear() }} LYNEGO PLOMBERIE. Tous droits réservés.</p>
          <div class="flex space-x-4 mt-4 md:mt-0">
            <a href="#" class="text-gray-400 hover:text-white transition-colors">
              <Facebook class="w-5 h-5" />
            </a>
            <a href="#" class="text-gray-400 hover:text-white transition-colors">
              <Instagram class="w-5 h-5" />
            </a>
            <a href="#" class="text-gray-400 hover:text-white transition-colors">
              <MapPin class="w-5 h-5" />
            </a>
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup lang="ts">
import { Phone, Clock, Facebook, Instagram, MapPin } from 'lucide-vue-next';

const navItems = [
  { name: 'Accueil', path: '/' },
  { name: 'À propos', path: '/about' },
  { name: 'Services', path: '/services' },
  { name: 'Réalisations', path: '/gallery' },
  { name: 'Avis', path: '/reviews' },
  { name: 'Contact', path: '/contact' },
];

const services = [
  'Débouchage urgent',
  'Rénovation de salle de bain',
  'Recherche de fuites',
  'Réparation de chauffe-eau',
  'Installation sanitaire',
];
</script>