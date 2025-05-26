<template>
  <div>
    <!-- Hero Section -->
    <section class="pt-20 pb-16 bg-primary-900 text-white">
      <div class="container-custom">
        <div class="text-center max-w-3xl mx-auto reveal">
          <h1 class="text-4xl md:text-5xl font-bold mb-6">Avis Clients</h1>
          <div class="flex justify-center items-center mb-4">
            <div class="flex">
              <Star
                v-for="i in 5"
                :key="i"
                class="w-7 h-7 text-yellow-400"
                fill="currentColor"
              />
            </div>
            <span class="ml-2 text-2xl font-semibold">5.0 sur 5</span>
          </div>
          <p class="text-xl text-primary-100">
            Découvrez ce que nos clients disent de nos services de plomberie.
          </p>
        </div>
      </div>
    </section>

    <!-- Reviews Section -->
    <section class="py-16 bg-white">
      <div class="container-custom">
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
          <div
            v-for="(review, index) in reviews"
            :key="index"
            class="bg-gray-50 p-8 rounded-lg shadow-md reveal"
            :style="{ animationDelay: `${index * 0.1}s` }"
            v-motion-slide-visible-once-bottom
          >
            <div class="flex items-center mb-4">
              <div class="flex">
                <Star
                  v-for="i in 5"
                  :key="i"
                  class="w-5 h-5 text-yellow-400"
                  fill="currentColor"
                />
              </div>
            </div>

            <p class="text-gray-700 mb-6 italic">"{{ review.text }}"</p>

            <div class="flex items-center">
              <div
                class="bg-primary-100 rounded-full w-12 h-12 flex items-center justify-center text-primary-700 font-bold text-lg"
              >
                {{ review.name.charAt(0) }}
              </div>
              <div class="ml-4">
                <h4 class="font-semibold text-lg">{{ review.name }}</h4>
                <div class="flex items-center text-sm text-gray-500">
                  <Clock class="w-4 h-4 mr-1" />
                  <span>{{ review.date }}</span>
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- Review Stats -->
        <div class="mt-16 bg-gray-50 p-8 rounded-lg shadow-md reveal">
          <div class="text-center mb-8">
            <h2 class="text-3xl font-bold mb-2">
              Statistiques de satisfaction
            </h2>
            <p class="text-gray-600">
              Voici ce que nos clients pensent de nos différents services.
            </p>
          </div>

          <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
            <div>
              <div v-for="(stat, index) in stats" :key="index" class="mb-4">
                <div class="flex justify-between mb-2">
                  <span class="font-medium">{{ stat.name }}</span>
                  <span class="font-semibold">{{ stat.rating }}/5</span>
                </div>
                <div class="w-full bg-gray-200 rounded-full h-2.5">
                  <div
                    class="bg-primary-500 h-2.5 rounded-full"
                    :style="{ width: `${stat.percentage}%` }"
                  ></div>
                </div>
              </div>
            </div>

            <div class="flex items-center justify-center">
              <div class="text-center">
                <div class="relative inline-block">
                  <div
                    class="w-36 h-36 rounded-full border-8 border-primary-500 flex items-center justify-center"
                  >
                    <span class="text-4xl font-bold text-primary-700"
                      >100%</span
                    >
                  </div>
                  <div
                    class="absolute -top-2 -right-2 bg-accent-500 text-white rounded-full w-12 h-12 flex items-center justify-center"
                  >
                    <ThumbsUp class="w-6 h-6" />
                  </div>
                </div>
                <p class="mt-4 text-lg font-semibold">Clients satisfaits</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Leave a Review Section -->
    <section class="py-16 bg-gray-50">
      <div class="container-custom text-center reveal">
        <h2 class="text-3xl font-bold mb-4">Votre Avis Compte</h2>
        <p class="text-lg text-gray-600 mb-8 max-w-2xl mx-auto">
          Vous avez fait appel à nos services ? Partagez votre expérience en
          laissant un avis.
        </p>

        <a
          href="https://www.google.com/maps/place/LYNEGO+PLOMBERIE/@45.8803093,4.701886,15z/data=!4m18!1m9!3m8!1s0x29c2bb60393810b1:0xe72ecb7de6f74312!2sLYNEGO+PLOMBERIE!8m2!3d45.8803093!4d4.701886!9m1!1b1!16s%2Fg%2F11w31f0f7g!3m7!1s0x29c2bb60393810b1:0xe72ecb7de6f74312!8m2!3d45.8803093!4d4.701886!9m1!1b1!16s%2Fg%2F11w31f0f7g?entry=ttu&g_ep=EgoyMDI1MDUyMS4wIKXMDSoASAFQAw%3D%3D"
          target="_blank"
          rel="noopener noreferrer"
          class="btn bg-primary-600 hover:bg-primary-700 text-white px-8 py-4 rounded-lg font-semibold inline-flex items-center justify-center"
        >
          <Star class="w-5 h-5 mr-2" />
          Laisser un avis sur Google
        </a>
      </div>
    </section>

    <!-- CTA Section -->
    <section class="py-16 bg-primary-900 text-white">
      <div class="container-custom text-center reveal">
        <h2 class="text-3xl md:text-4xl font-bold mb-6">
          Rejoignez nos clients satisfaits
        </h2>
        <p class="text-xl mb-8 max-w-3xl mx-auto">
          Faites confiance à notre expertise pour tous vos besoins en plomberie
          et bénéficiez d'un service d'excellence.
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
            Nous Contacter
          </router-link>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup lang="ts">
import { Star, Phone, MessageSquare, Clock, ThumbsUp } from "lucide-vue-next";

// Set document title
import { onMounted } from "vue";
onMounted(() => {
  document.title = "Avis Clients - LYNEGO PLOMBERIE";
});

const reviews = [
  {
    name: "Catia Rodrigues Morais",
    text: "Entreprise réactive et ponctuelle. Nous avons appeler tard dans la soirée pour un débouchage WC urgent, contre toute attente nous avons été surpris de la rapidité d'intervention. Un jeune homme sympathique et très professionnel. Je recommande. Merci beaucoup!",
    date: "Il y a 2 mois",
  },
  {
    name: "Mora Garage",
    text: "Ce monsieur est intervenu dans la journée de mon appel et a réparé juste ce qu'il fallait (et pourtant femme seule, il aurait clairement pu en profiter....) je recommande vraiment, très professionnel!",
    date: "Il y a 3 mois",
  },
  {
    name: "Anthony Dalessandro",
    text: "Nous avons fait appel à cette entreprise pour une rénovation de salle de bain. Nous sommes super content du résultat. Entreprise sérieuse et compétente 👌",
    date: "Il y a 1 mois",
  },
  {
    name: "Theliau Petit",
    text: "Extrêmement réactif et très agréable! Prix tout à fait correct. Je vous recommande grandement!",
    date: "Il y a 2 semaines",
  },
];

const stats = [
  { name: "Qualité du service", rating: 5.0, percentage: 100 },
  { name: "Ponctualité", rating: 5.0, percentage: 100 },
  { name: "Expertise technique", rating: 5.0, percentage: 100 },
  { name: "Rapport qualité-prix", rating: 4.9, percentage: 98 },
  { name: "Communication", rating: 5.0, percentage: 100 },
];
</script>
