<template>
  <div>
    <!-- Hero Section -->
    <section class="pt-20 pb-16 bg-primary-900 text-white">
      <div class="container-custom">
        <div class="text-center max-w-3xl mx-auto reveal">
          <h1 class="text-4xl md:text-5xl font-bold mb-6">Contactez-Nous</h1>
          <p class="text-xl text-primary-100">
            Nous sommes disponibles 24h/24 et 7j/7 pour répondre à toutes vos
            urgences de plomberie.
          </p>
        </div>
      </div>
    </section>

    <!-- Contact Information & Form -->
    <section class="py-16 bg-white">
      <div class="container-custom">
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-12">
          <!-- Contact Information -->
          <div class="reveal" v-motion-slide-visible-once-right>
            <h2 class="text-3xl font-bold mb-4">Nos Coordonnées</h2>
            <div class="w-24 h-1 bg-primary-500 mb-6"></div>

            <div class="bg-gray-50 p-8 rounded-lg shadow-md mb-8">
              <div class="flex items-center mb-6">
                <div class="bg-primary-100 p-3 rounded-full mr-4">
                  <Phone class="w-6 h-6 text-primary-600" />
                </div>
                <div>
                  <h3 class="font-semibold text-lg mb-1">Téléphone</h3>
                  <a
                    href="tel:0778646262"
                    class="text-primary-600 hover:underline"
                    >0778646262</a
                  >
                </div>
              </div>

              <div class="flex items-center mb-6">
                <div class="bg-primary-100 p-3 rounded-full mr-4">
                  <Clock class="w-6 h-6 text-primary-600" />
                </div>
                <div>
                  <h3 class="font-semibold text-lg mb-1">Heures d'ouverture</h3>
                  <p>Ouvert 24h/24 – 7j/7</p>
                </div>
              </div>

              <div class="flex items-center">
                <div class="bg-primary-100 p-3 rounded-full mr-4">
                  <MapPin class="w-6 h-6 text-primary-600" />
                </div>
                <div>
                  <h3 class="font-semibold text-lg mb-1">
                    Zone d'intervention
                  </h3>
                  <p>Intervention rapide partout près de chez vous</p>
                </div>
              </div>
            </div>

            <div class="bg-accent-500 text-white p-6 rounded-lg shadow-md">
              <h3 class="text-xl font-semibold mb-4 flex items-center">
                <AlertTriangle class="w-6 h-6 mr-2" />
                Besoin d'une intervention urgente ?
              </h3>
              <p class="mb-4">
                N'attendez pas ! Contactez-nous immédiatement pour une
                intervention rapide.
              </p>
              <a
                href="tel:0778646262"
                class="pulse-button w-full btn bg-white text-accent-600 hover:bg-gray-100 px-6 py-3 rounded-lg font-semibold inline-flex items-center justify-center"
              >
                <Phone class="w-5 h-5 mr-2" />
                Appel d'Urgence
              </a>
            </div>
          </div>

          <!-- Contact Form -->
          <div class="reveal">
            <h2 class="text-3xl font-bold mb-4">Envoyez-nous un Message</h2>
            <div class="w-24 h-1 bg-primary-500 mb-6"></div>

            <form
              @submit.prevent="submitForm"
              class="bg-gray-50 p-8 rounded-lg shadow-md"
            >
              <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-6">
                <div>
                  <label
                    for="firstName"
                    class="block text-sm font-medium text-gray-700 mb-1"
                    >Prénom</label
                  >
                  <input
                    type="text"
                    id="firstName"
                    v-model="form.firstName"
                    class="w-full px-4 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-primary-500"
                    placeholder="Votre prénom"
                    required
                  />
                </div>

                <div>
                  <label
                    for="lastName"
                    class="block text-sm font-medium text-gray-700 mb-1"
                    >Nom</label
                  >
                  <input
                    type="text"
                    id="lastName"
                    v-model="form.lastName"
                    class="w-full px-4 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-primary-500"
                    placeholder="Votre nom"
                    required
                  />
                </div>
              </div>

              <div class="mb-6">
                <label
                  for="phone"
                  class="block text-sm font-medium text-gray-700 mb-1"
                  >Téléphone</label
                >
                <input
                  type="tel"
                  id="phone"
                  v-model="form.phone"
                  class="w-full px-4 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-primary-500"
                  placeholder="Votre numéro de téléphone"
                  required
                />
              </div>

              <div class="mb-6">
                <label
                  for="email"
                  class="block text-sm font-medium text-gray-700 mb-1"
                  >Email</label
                >
                <input
                  type="email"
                  id="email"
                  v-model="form.email"
                  class="w-full px-4 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-primary-500"
                  placeholder="Votre adresse email"
                />
              </div>

              <div class="mb-6">
                <label
                  for="service"
                  class="block text-sm font-medium text-gray-700 mb-1"
                  >Service souhaité</label
                >
                <select
                  id="service"
                  v-model="form.service"
                  class="w-full px-4 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-primary-500"
                >
                  <option value="">Sélectionnez un service</option>
                  <option
                    v-for="service in services"
                    :key="service"
                    :value="service"
                  >
                    {{ service }}
                  </option>
                </select>
              </div>

              <div class="mb-6">
                <label
                  for="message"
                  class="block text-sm font-medium text-gray-700 mb-1"
                  >Message</label
                >
                <textarea
                  id="message"
                  v-model="form.message"
                  rows="4"
                  class="w-full px-4 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-primary-500"
                  placeholder="Décrivez votre problème ou votre demande"
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
    </section>

    <!-- Map Section -->
    <section class="py-16 bg-gray-50">
      <div class="container-custom">
        <div class="text-center mb-12 reveal">
          <h2 class="text-3xl font-bold mb-4">Zone d'Intervention</h2>
          <div class="w-24 h-1 bg-primary-500 mx-auto mb-6"></div>
          <p class="text-lg text-gray-600 max-w-2xl mx-auto">
            Nous intervenons rapidement dans toute la région. N'hésitez pas à
            nous contacter pour vérifier notre disponibilité dans votre secteur.
          </p>
        </div>

        <div class="rounded-lg overflow-hidden shadow-lg reveal">
          <!-- Map would go here - This is a placeholder that would be replaced with an actual map embed -->
          <div class="bg-gray-200 w-full h-96 flex items-center justify-center">
            <MapPin class="w-12 h-12 text-primary-500" />
            <span class="ml-2 text-xl font-semibold"
              >Carte de la zone d'intervention</span
            >
          </div>
        </div>
      </div>
    </section>

    <!-- FAQ Section -->
    <section class="py-16 bg-white">
      <div class="container-custom">
        <div class="text-center mb-12 reveal">
          <h2 class="text-3xl font-bold mb-4">Questions Fréquentes</h2>
          <div class="w-24 h-1 bg-primary-500 mx-auto mb-6"></div>
          <p class="text-lg text-gray-600 max-w-2xl mx-auto">
            Trouvez rapidement des réponses à vos questions les plus courantes.
          </p>
        </div>

        <div class="max-w-3xl mx-auto reveal">
          <div v-for="(faq, index) in faqs" :key="index" class="mb-4">
            <button
              @click="toggleFaq(index)"
              class="flex justify-between items-center w-full p-5 bg-gray-50 rounded-lg text-left focus:outline-none"
              :class="{ 'bg-primary-50': activeFaq === index }"
            >
              <span class="font-semibold text-lg">{{ faq.question }}</span>
              <ChevronDown
                class="w-5 h-5 transition-transform duration-300"
                :class="{ 'transform rotate-180': activeFaq === index }"
              />
            </button>
            <div
              v-show="activeFaq === index"
              class="p-5 bg-gray-50 rounded-b-lg mt-px border-t border-gray-200"
            >
              <p class="text-gray-700">{{ faq.answer }}</p>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";
import {
  Phone,
  Clock,
  MapPin,
  AlertTriangle,
  ChevronDown,
} from "lucide-vue-next";

// Set document title
import { onMounted } from "vue";
onMounted(() => {
  document.title = "Contact - LYNEGO PLOMBERIE";
});

const form = ref({
  firstName: "",
  lastName: "",
  email: "",
  phone: "",
  service: "",
  message: "",
});

const services = [
  "Débouchage urgent",
  "Rénovation de salle de bain",
  "Recherche de fuites",
  "Réparation de chauffe-eau",
  "Installation sanitaire",
  "Autre demande",
];

const submitForm = () => {
  // In a real application, you would send the form data to a server
  alert(
    `Merci ${form.value.firstName} ${form.value.lastName}! Nous vous contacterons très rapidement au ${form.value.phone}.`
  );
  // Reset form
  form.value = {
    firstName: "",
    lastName: "",
    email: "",
    phone: "",
    service: "",
    message: "",
  };
};

const faqs = [
  {
    question: "Dans quels délais intervenez-vous en cas d'urgence ?",
    answer:
      "Nous intervenons généralement dans l'heure qui suit votre appel pour les urgences. Notre équipe est disponible 24h/24 et 7j/7 pour répondre rapidement à vos problèmes de plomberie urgents.",
  },
  {
    question: "Proposez-vous des devis gratuits ?",
    answer:
      "Oui, nous proposons des devis gratuits et détaillés pour tous nos services. Contactez-nous par téléphone ou via notre formulaire pour obtenir une estimation précise de vos travaux.",
  },
  {
    question: "Quelle est votre zone d'intervention ?",
    answer:
      "Nous intervenons dans toute la région. N'hésitez pas à nous contacter pour vérifier notre disponibilité dans votre secteur.",
  },
  {
    question: "Vos travaux sont-ils garantis ?",
    answer:
      "Oui, tous nos travaux sont garantis. Nous nous engageons à fournir un service de qualité et à assurer un suivi après intervention si nécessaire.",
  },
  {
    question: "Quels moyens de paiement acceptez-vous ?",
    answer:
      "Nous acceptons les paiements par carte bancaire, espèces et chèques. Des facilités de paiement peuvent également être proposées pour les travaux importants.",
  },
];

const activeFaq = ref(-1);

const toggleFaq = (index: number) => {
  if (activeFaq.value === index) {
    activeFaq.value = -1;
  } else {
    activeFaq.value = index;
  }
};
</script>
