<template>
  <section class="py-16 bg-white">
    <div class="container-custom">
      <div class="text-center mb-12 reveal">
        <h2 class="text-3xl md:text-4xl font-bold mb-4">Avis de Nos Clients</h2>
        <div class="w-24 h-1 bg-primary-500 mx-auto mb-6"></div>
        <div class="flex justify-center items-center mb-4">
          <div class="flex">
            <Star v-for="i in 5" :key="i" class="w-6 h-6 text-yellow-400" fill="currentColor" />
          </div>
          <span class="ml-2 text-xl font-semibold">5.0 sur 5</span>
        </div>
        <p class="text-lg text-gray-600 max-w-2xl mx-auto">
          Découvrez ce que nos clients disent de nos services.
        </p>
      </div>
      
      <div class="relative reveal">
        <swiper
          :modules="[SwiperAutoplay, SwiperPagination, SwiperNavigation]"
          :slides-per-view="1"
          :space-between="30"
          :breakpoints="{
            '640': {
              slidesPerView: 1,
              spaceBetween: 20,
            },
            '768': {
              slidesPerView: 2,
              spaceBetween: 30,
            },
            '1024': {
              slidesPerView: 2,
              spaceBetween: 40,
            },
          }"
          :autoplay="{
            delay: 5000,
            disableOnInteraction: false,
          }"
          :pagination="{ clickable: true }"
          :navigation="true"
          class="mySwiper"
        >
          <swiper-slide v-for="(review, index) in reviews" :key="index">
            <div class="bg-gray-50 p-6 rounded-lg shadow-md h-full flex flex-col">
              <div class="flex items-center mb-4">
                <div class="flex">
                  <Star v-for="i in 5" :key="i" class="w-5 h-5 text-yellow-400" fill="currentColor" />
                </div>
              </div>
              <p class="text-gray-700 mb-6 flex-grow">{{ review.text }}</p>
              <div class="flex items-center mt-auto">
                <div class="bg-primary-100 rounded-full w-10 h-10 flex items-center justify-center text-primary-700 font-bold">
                  {{ review.name.charAt(0) }}
                </div>
                <div class="ml-3">
                  <h4 class="font-semibold">{{ review.name }}</h4>
                </div>
              </div>
            </div>
          </swiper-slide>
        </swiper>
      </div>
      
      <div class="text-center mt-12 reveal">
        <router-link to="/reviews" class="btn btn-primary">
          Voir tous les avis
          <ArrowRight class="w-5 h-5 ml-2" />
        </router-link>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { Star, ArrowRight } from 'lucide-vue-next';
import { Swiper, SwiperSlide } from 'swiper/vue';
import { Autoplay, Pagination, Navigation } from 'swiper/modules';
import 'swiper/css';
import 'swiper/css/pagination';
import 'swiper/css/navigation';

// Rename for clarity
const SwiperAutoplay = Autoplay;
const SwiperPagination = Pagination;
const SwiperNavigation = Navigation;

const reviews = [
  {
    name: 'Catia Rodrigues Morais',
    text: 'Entreprise réactive et ponctuelle. Nous avons appeler tard dans la soirée pour un débouchage WC urgent, contre toute attente nous avons été surpris de la rapidité d\'intervention. Un jeune homme sympathique et très professionnel. Je recommande. Merci beaucoup!'
  },
  {
    name: 'Mora Garage',
    text: 'Ce monsieur est intervenu dans la journée de mon appel et a réparé juste ce qu\'il fallait (et pourtant femme seule, il aurait clairement pu en profiter....) je recommande vraiment, très professionnel!'
  },
  {
    name: 'Anthony Dalessandro',
    text: 'Nous avons fait appel à cette entreprise pour une rénovation de salle de bain. Nous sommes super content du résultat. Entreprise sérieuse et compétente 👌'
  },
  {
    name: 'Theliau Petit',
    text: 'Extrêmement réactif et très agréable! Prix tout à fait correct. Je vous recommande grandement!'
  }
];
</script>

<style scoped>
.swiper {
  width: 100%;
  padding-bottom: 50px;
}

:deep(.swiper-pagination-bullet) {
  background: theme('colors.primary.500');
}

:deep(.swiper-button-next),
:deep(.swiper-button-prev) {
  color: theme('colors.primary.500');
}
</style>