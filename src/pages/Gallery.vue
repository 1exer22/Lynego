<template>
  <div>
    <!-- Hero Section -->
    <section class="pt-20 pb-16 bg-primary-900 text-white">
      <div class="container-custom">
        <div class="text-center max-w-3xl mx-auto reveal">
          <h1 class="text-4xl md:text-5xl font-bold mb-6">Nos Réalisations</h1>
          <p class="text-xl text-primary-100">
            Découvrez nos travaux récents et la qualité de nos services de
            plomberie.
          </p>
        </div>
      </div>
    </section>

    <!-- Gallery Filters -->
    <section class="py-8 bg-white border-b">
      <div class="container-custom">
        <div class="flex flex-wrap items-center justify-center gap-4 reveal">
          <button
            @click="activeFilter = 'all'"
            :class="[
              'px-4 py-2 rounded-md transition-colors',
              activeFilter === 'all'
                ? 'bg-primary-500 text-white'
                : 'bg-gray-100 text-gray-700 hover:bg-gray-200',
            ]"
          >
            Tous les projets
          </button>

          <button
            v-for="filter in filters"
            :key="filter.value"
            @click="activeFilter = filter.value"
            :class="[
              'px-4 py-2 rounded-md transition-colors',
              activeFilter === filter.value
                ? 'bg-primary-500 text-white'
                : 'bg-gray-100 text-gray-700 hover:bg-gray-200',
            ]"
          >
            {{ filter.label }}
          </button>
        </div>
      </div>
    </section>

    <!-- Gallery Grid -->
    <section class="py-12 bg-gray-50">
      <div class="container-custom">
        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
          <div
            v-for="(image, index) in filteredImages"
            :key="index"
            class="reveal overflow-hidden rounded-lg shadow-md cursor-pointer"
            :style="{ animationDelay: `${index * 0.1}s` }"
            @click="openLightbox(index)"
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
                  <div class="mt-4">
                    <span
                      class="inline-block bg-white/20 px-3 py-1 rounded-full text-sm"
                    >
                      {{ image.category }}
                    </span>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Lightbox -->
    <div
      v-if="lightboxOpen"
      class="fixed inset-0 bg-black/90 z-50 flex items-center justify-center"
    >
      <div class="relative w-full max-w-5xl p-4">
        <!-- Close button -->
        <button
          @click="closeLightbox"
          class="absolute top-4 right-4 text-white z-10 bg-black/50 rounded-full p-2 hover:bg-black"
        >
          <X class="w-6 h-6" />
        </button>

        <!-- Navigation -->
        <button
          @click="prevImage"
          class="absolute left-4 top-1/2 transform -translate-y-1/2 text-white z-10 bg-black/50 rounded-full p-2 hover:bg-black"
        >
          <ChevronLeft class="w-6 h-6" />
        </button>

        <button
          @click="nextImage"
          class="absolute right-4 top-1/2 transform -translate-y-1/2 text-white z-10 bg-black/50 rounded-full p-2 hover:bg-black"
        >
          <ChevronRight class="w-6 h-6" />
        </button>

        <!-- Image -->
        <div class="bg-white rounded-lg overflow-hidden">
          <img
            :src="filteredImages[currentImageIndex].url"
            :alt="filteredImages[currentImageIndex].alt"
            class="w-full h-auto max-h-[80vh] object-contain"
          />

          <div class="p-4 bg-white">
            <h3 class="text-xl font-semibold mb-2">
              {{ filteredImages[currentImageIndex].title }}
            </h3>
            <p class="text-gray-600">
              {{ filteredImages[currentImageIndex].description }}
            </p>
            <div class="mt-2">
              <span
                class="inline-block bg-primary-100 text-primary-800 px-3 py-1 rounded-full text-sm"
              >
                {{ filteredImages[currentImageIndex].category }}
              </span>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- CTA Section -->
    <section class="py-16 bg-primary-900 text-white">
      <div class="container-custom text-center reveal">
        <h2 class="text-3xl md:text-4xl font-bold mb-6">
          Prêt à démarrer votre projet ?
        </h2>
        <p class="text-xl mb-8 max-w-3xl mx-auto">
          Contactez-nous dès aujourd'hui pour discuter de vos besoins en
          plomberie et obtenir un devis gratuit.
        </p>

        <div class="flex flex-col sm:flex-row justify-center gap-4">
          <a
            href="tel:0778646262"
            class="btn bg-accent-500 hover:bg-accent-600 text-white px-8 py-4 rounded-lg font-semibold inline-flex items-center justify-center"
          >
            <Phone class="w-5 h-5 mr-2" />
            Appeler Maintenant
          </a>

          <router-link
            to="/contact"
            class="btn bg-white hover:bg-gray-100 text-primary-800 px-8 py-4 rounded-lg font-semibold inline-flex items-center justify-center"
          >
            <MessageSquare class="w-5 h-5 mr-2" />
            Demander un Devis
          </router-link>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup lang="ts">
import { ref, computed, onMounted, onUnmounted } from "vue";
import {
  Phone,
  MessageSquare,
  X,
  ChevronLeft,
  ChevronRight,
} from "lucide-vue-next";

// Set document title
onMounted(() => {
  document.title = "Nos Réalisations - LYNEGO PLOMBERIE";
  // Add ESC key listener for lightbox
  document.addEventListener("keydown", handleKeyDown);
});

onUnmounted(() => {
  document.removeEventListener("keydown", handleKeyDown);
});

const filters = [
  { label: "Rénovations", value: "renovation" },
  { label: "Dépannages", value: "depannage" },
  { label: "Installations", value: "installation" },
  { label: "Salles de bain", value: "salle-de-bain" },
];

const galleryImages = [
  {
    url: new URL("../assets/1.jpg", import.meta.url).href,
    alt: "Réalisation 1",
    title: "Réalisation 1",
    description: "Réalisation 1",
    category: "Rénovations",
    filter: "renovation salle-de-bain",
  },
  {
    url: new URL("../assets/2.jpg", import.meta.url).href,
    alt: "Réalisation 2",
    title: "Réalisation 2",
    description: "Réalisation 2",
    category: "Rénovations",
    filter: "renovation",
  },
  {
    url: new URL("../assets/3.jpg", import.meta.url).href,
    alt: "Salle de bain moderne",
    title: "Salle de Bain Moderne",
    description: "Réalisation d’une salle de bain contemporaine et élégante.",
    category: "Rénovations",
    filter: "renovation salle-de-bain",
  },
  {
    url: new URL("../assets/4.jpg", import.meta.url).href,
    alt: "Réalisation 4",
    title: "Réalisation 4",
    description: "Réalisation 4",
    category: "Rénovations",
    filter: "renovation",
  },
  {
    url: new URL("../assets/5.jpg", import.meta.url).href,
    alt: "Salle de bain moderne",
    title: "Salle de Bain Moderne",
    description: "Réalisation d’une salle de bain contemporaine et élégante.",
    category: "Rénovations",
    filter: "renovation salle-de-bain",
  },
  {
    url: new URL("../assets/6.jpg", import.meta.url).href,
    alt: "Réalisation 6",
    title: "Réalisation 6",
    description: "Réalisation 6",
    category: "Rénovations",
    filter: "renovation",
  },
];

const activeFilter = ref("all");
const lightboxOpen = ref(false);
const currentImageIndex = ref(0);

const filteredImages = computed(() => {
  if (activeFilter.value === "all") {
    return galleryImages;
  }

  return galleryImages.filter((image) =>
    image.filter.includes(activeFilter.value)
  );
});

const openLightbox = (index: number) => {
  currentImageIndex.value = index;
  lightboxOpen.value = true;
  document.body.style.overflow = "hidden";
};

const closeLightbox = () => {
  lightboxOpen.value = false;
  document.body.style.overflow = "";
};

const nextImage = () => {
  currentImageIndex.value =
    (currentImageIndex.value + 1) % filteredImages.value.length;
};

const prevImage = () => {
  currentImageIndex.value =
    (currentImageIndex.value - 1 + filteredImages.value.length) %
    filteredImages.value.length;
};

const handleKeyDown = (e: KeyboardEvent) => {
  if (!lightboxOpen.value) return;

  switch (e.key) {
    case "Escape":
      closeLightbox();
      break;
    case "ArrowRight":
      nextImage();
      break;
    case "ArrowLeft":
      prevImage();
      break;
  }
};
</script>
