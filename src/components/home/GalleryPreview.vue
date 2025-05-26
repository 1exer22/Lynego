<template>
  <section class="py-16 bg-gray-50">
    <div class="container-custom">
      <div class="text-center mb-12 reveal">
        <h2 class="text-3xl md:text-4xl font-bold mb-4">Nos Réalisations</h2>
        <div class="w-24 h-1 bg-primary-500 mx-auto mb-6"></div>
        <p class="text-lg text-gray-600 max-w-2xl mx-auto">
          Découvrez quelques-unes de nos réalisations récentes pour des clients
          satisfaits.
        </p>
      </div>

      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
        <div
          v-for="(image, index) in galleryImages.slice(0, 6)"
          :key="index"
          class="reveal overflow-hidden rounded-lg shadow-md"
          :style="{ animationDelay: `${index * 0.1}s` }"
        >
          <div class="relative group h-64">
            <img
              :src="image.url"
              :alt="image.alt"
              class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-110"
            />
            <div
              class="absolute inset-0 bg-primary-900/60 opacity-0 group-hover:opacity-100 flex items-center justify-center transition-opacity duration-300"
            >
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
import { ArrowRight } from "lucide-vue-next";

const galleryImages = [
  {
    url: new URL("../../assets/1.jpg", import.meta.url).href,
    alt: "Salle de bain moderne",
    title: "Salle de Bain Moderne",
    description: "Réalisation d’une salle de bain contemporaine et élégante.",
  },
  {
    url: new URL("../../assets/2.jpg", import.meta.url).href,
    alt: "Salon design",
    title: "Salon Design",
    description: "Aménagement d’un salon moderne et lumineux.",
  },
  {
    url: new URL("../../assets/3.jpg", import.meta.url).href,
    alt: "Réalisation 3",
    title: "Réalisation 3",
    description: "Projet de rénovation et d’installation sanitaire.",
  },
  {
    url: new URL("../../assets/4.jpg", import.meta.url).href,
    alt: "Réalisation 4",
    title: "Réalisation 4",
    description: "Exemple de salle de bain ou cuisine rénovée.",
  },
  {
    url: new URL("../../assets/5.jpg", import.meta.url).href,
    alt: "Réalisation 5",
    title: "Réalisation 5",
    description: "Installation de plomberie moderne.",
  },
  {
    url: new URL("../../assets/6.jpg", import.meta.url).href,
    alt: "Réalisation 6",
    title: "Réalisation 6",
    description: "Autre projet de rénovation ou dépannage.",
  },
];
</script>
