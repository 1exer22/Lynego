<template>
  <div>
    <!-- Hero Section -->
    <section class="pt-20 pb-16 bg-primary-900 text-white">
      <div class="container-custom">
        <div class="text-center max-w-3xl mx-auto reveal">
          <h1 class="text-4xl md:text-5xl font-bold mb-6">Nos Services</h1>
          <p class="text-xl text-primary-100">
            Des solutions de plomberie professionnelles pour tous vos besoins,
            disponibles 24h/24 et 7j/7.
          </p>
        </div>
      </div>
    </section>

    <!-- Services Section -->
    <section class="py-16 bg-white">
      <div class="container-custom">
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
          <div
            v-for="(service, index) in services"
            :key="index"
            class="card card-hover reveal"
            :style="{ animationDelay: `${index * 0.1}s` }"
          >
            <div class="relative h-48 overflow-hidden">
              <img
                :src="service.image"
                :alt="service.title"
                class="w-full h-full object-cover"
              />
              <div class="absolute inset-0 bg-primary-900/30"></div>
            </div>
            <div class="p-6">
              <div
                class="bg-primary-100 p-3 rounded-full w-14 h-14 flex items-center justify-center mb-4 -mt-10 relative z-10 border-4 border-white"
              >
                <component
                  :is="service.icon"
                  class="w-7 h-7 text-primary-600"
                />
              </div>
              <h3 class="text-xl font-semibold mb-3">{{ service.title }}</h3>
              <p class="text-gray-600 mb-4">{{ service.description }}</p>
              <ul class="text-gray-600 mb-4 space-y-2">
                <li
                  v-for="(feature, i) in service.features"
                  :key="i"
                  class="flex items-start"
                >
                  <CheckCircle
                    class="w-5 h-5 text-primary-500 mr-2 mt-0.5 flex-shrink-0"
                  />
                  <span>{{ feature }}</span>
                </li>
              </ul>
              <a
                href="tel:0778646262"
                class="btn btn-primary mt-2 w-full flex items-center justify-center"
              >
                <Phone class="w-5 h-5 mr-2" />
                Demander un devis
              </a>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Why Choose Us -->
    <section class="py-16 bg-gray-50">
      <div class="container-custom">
        <div class="text-center mb-12 reveal">
          <h2 class="text-3xl md:text-4xl font-bold mb-4">
            Pourquoi Choisir LYNEGO PLOMBERIE ?
          </h2>
          <div class="w-24 h-1 bg-primary-500 mx-auto mb-6"></div>
          <p class="text-lg text-gray-600 max-w-2xl mx-auto">
            Nous nous engageons à offrir un service de plomberie exceptionnel
            avec une garantie de satisfaction.
          </p>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 gap-8 reveal">
          <div class="bg-white p-6 rounded-lg shadow-md flex items-start">
            <div class="bg-primary-100 p-3 rounded-full flex-shrink-0 mr-4">
              <Clock class="w-6 h-6 text-primary-600" />
            </div>
            <div>
              <h3 class="text-xl font-semibold mb-2">Disponibilité 24h/24</h3>
              <p class="text-gray-600">
                Nous sommes disponibles jour et nuit, tous les jours de l'année
                pour répondre à vos urgences.
              </p>
            </div>
          </div>

          <div class="bg-white p-6 rounded-lg shadow-md flex items-start">
            <div class="bg-primary-100 p-3 rounded-full flex-shrink-0 mr-4">
              <Zap class="w-6 h-6 text-primary-600" />
            </div>
            <div>
              <h3 class="text-xl font-semibold mb-2">Intervention Rapide</h3>
              <p class="text-gray-600">
                Nous intervenons rapidement dans votre secteur pour résoudre vos
                problèmes de plomberie sans délai.
              </p>
            </div>
          </div>

          <div class="bg-white p-6 rounded-lg shadow-md flex items-start">
            <div class="bg-primary-100 p-3 rounded-full flex-shrink-0 mr-4">
              <Shield class="w-6 h-6 text-primary-600" />
            </div>
            <div>
              <h3 class="text-xl font-semibold mb-2">Travail Garanti</h3>
              <p class="text-gray-600">
                Tous nos travaux sont garantis. Nous ne sommes satisfaits que
                lorsque vous l'êtes.
              </p>
            </div>
          </div>

          <div class="bg-white p-6 rounded-lg shadow-md flex items-start">
            <div class="bg-primary-100 p-3 rounded-full flex-shrink-0 mr-4">
              <DollarSign class="w-6 h-6 text-primary-600" />
            </div>
            <div>
              <h3 class="text-xl font-semibold mb-2">Prix Transparents</h3>
              <p class="text-gray-600">
                Nous offrons des devis détaillés sans frais cachés pour une
                totale transparence.
              </p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- CTA Section -->
    <section class="py-16 bg-primary-900 text-white">
      <div class="container-custom text-center reveal">
        <h2 class="text-3xl md:text-4xl font-bold mb-6">
          Besoin d'un plombier maintenant ?
        </h2>
        <p class="text-xl mb-8 max-w-3xl mx-auto">
          N'attendez pas ! Contactez-nous pour une intervention rapide et
          professionnelle.
        </p>

        <div class="flex flex-col sm:flex-row justify-center gap-4">
          <a
            href="tel:0778646262"
            class="pulse-button btn bg-accent-500 hover:bg-accent-600 text-white px-8 py-4 rounded-lg font-semibold inline-flex items-center justify-center"
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
import {
  Phone,
  MessageSquare,
  Droplet,
  Bath,
  Search,
  Flame,
  Wrench,
  Clock,
  Zap,
  Shield,
  DollarSign,
  CheckCircle,
} from "lucide-vue-next";

// Set document title
import { onMounted } from "vue";
onMounted(() => {
  document.title = "Nos Services - LYNEGO PLOMBERIE";
});

const services = [
  {
    title: "Débouchage Urgent",
    description:
      "Service d'urgence pour déboucher vos canalisations et évacuations rapidement.",
    image: new URL("../assets/debouchage.jpeg", import.meta.url).href,
    icon: Droplet,
    features: [
      "Intervention rapide 24h/24",
      "Équipement professionnel",
      "Débouchage de WC, lavabos, éviers",
      "Nettoyage haute pression",
    ],
  },
  {
    title: "Rénovation de Salle de Bain",
    description:
      "Transformation complète de votre salle de bain selon vos envies et votre budget.",
    image: new URL("../assets/reno.jpeg", import.meta.url).href,
    icon: Bath,
    features: [
      "Conception personnalisée",
      "Installation complète",
      "Plomberie et carrelage",
      "Finitions de qualité",
    ],
  },
  {
    title: "Recherche de Fuites",
    description:
      "Détection précise et non destructive de toutes les fuites d'eau dans votre habitation.",
    image: new URL("../assets/fuite.jpeg", import.meta.url).href,
    icon: Search,
    features: [
      "Détection acoustique",
      "Caméra thermique",
      "Localisation précise",
      "Réparation immédiate",
    ],
  },
  {
    title: "Réparation de Chauffe-eau",
    description:
      "Dépannage et réparation de tous types de chauffe-eau et cumulus.",
    image: new URL("../assets/eau.jpeg", import.meta.url).href,
    icon: Flame,
    features: [
      "Diagnostic complet",
      "Réparation rapide",
      "Remplacement si nécessaire",
      "Toutes marques",
    ],
  },
  {
    title: "Installation Sanitaire",
    description:
      "Installation professionnelle de tous vos équipements sanitaires.",
    image: new URL("../assets/sanitaire.jpeg", import.meta.url).href,
    icon: Wrench,
    features: [
      "WC, lavabos, douches, baignoires",
      "Raccordements aux normes",
      "Conseils personnalisés",
      "Installation garantie",
    ],
  },
  {
    title: "Dépannage 24h/24",
    description:
      "Service d'urgence disponible jour et nuit pour tous vos problèmes de plomberie.",
    image: new URL("../assets/depannage.jpeg", import.meta.url).href,
    icon: Clock,
    features: [
      "Intervention rapide",
      "Équipe mobile disponible",
      "Réparations d'urgence",
      "Devis transparent",
    ],
  },
];
</script>
