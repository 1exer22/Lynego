<template>
  <header
    :class="[
      'fixed w-full z-50 transition-all duration-300',
      scrolled ? 'bg-white shadow-md py-2' : 'bg-transparent py-4',
    ]"
  >
    <div class="container-custom">
      <div class="flex justify-between items-center">
        <!-- Logo -->
        <router-link to="/" class="flex items-center">
          <span class="text-xl md:text-2xl font-bold text-primary-700"
            >LYNEGO PLOMBERIE</span
          >
        </router-link>

        <!-- Mobile menu button -->
        <button @click="isOpen = !isOpen" class="lg:hidden focus:outline-none">
          <span v-if="!isOpen" class="block w-6 h-px bg-gray-900 mb-1"></span>
          <span v-if="!isOpen" class="block w-6 h-px bg-gray-900 mb-1"></span>
          <span v-if="!isOpen" class="block w-6 h-px bg-gray-900"></span>
          <span
            v-else
            class="block w-6 h-px bg-gray-900 transform rotate-45 translate-y-1"
          ></span>
          <span
            v-else
            class="block w-6 h-px bg-gray-900 transform -rotate-45"
          ></span>
        </button>

        <!-- Desktop Navigation -->
        <nav class="hidden lg:flex space-x-8 items-center">
          <router-link
            v-for="item in navItems"
            :key="item.path"
            :to="item.path"
            class="text-gray-800 hover:text-primary-600 font-medium"
            :class="{ 'text-primary-600': $route.path === item.path }"
          >
            {{ item.name }}
          </router-link>
          <a href="tel:0778646262" class="btn btn-primary">
            <span class="mr-2">📞</span> 0778646262
          </a>
        </nav>
      </div>

      <!-- Mobile Navigation -->
      <div
        v-if="isOpen"
        class="lg:hidden mt-4 pb-4 fixed inset-0 bg-white bg-opacity-90 z-40"
      >
        <!-- Bouton de fermeture -->
        <button
          @click="isOpen = false"
          class="absolute top-4 right-4 text-3xl text-gray-700 focus:outline-none z-50"
        >
          &times;
        </button>
        <div class="flex flex-col space-y-3 p-6 mt-8">
          <router-link
            v-for="item in navItems"
            :key="item.path"
            :to="item.path"
            class="text-gray-800 hover:text-primary-600 font-medium py-2"
            :class="{ 'text-primary-600': $route.path === item.path }"
            @click="isOpen = false"
          >
            {{ item.name }}
          </router-link>
          <a href="tel:0778646262" class="btn btn-primary mt-4">
            <span class="mr-2">📞</span> 0778646262
          </a>
        </div>
      </div>
    </div>
  </header>
  <div :class="[scrolled ? 'h-16' : 'h-24']"></div>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted } from "vue";

const isOpen = ref(false);
const scrolled = ref(false);

const navItems = [
  { name: "Accueil", path: "/" },
  { name: "À propos", path: "/about" },
  { name: "Services", path: "/services" },
  { name: "Réalisations", path: "/gallery" },
  { name: "Avis", path: "/reviews" },
  { name: "Contact", path: "/contact" },
];

const checkScroll = () => {
  scrolled.value = window.scrollY > 50;
};

onMounted(() => {
  window.addEventListener("scroll", checkScroll);
  checkScroll(); // Check initial state
});

onUnmounted(() => {
  window.removeEventListener("scroll", checkScroll);
});
</script>
