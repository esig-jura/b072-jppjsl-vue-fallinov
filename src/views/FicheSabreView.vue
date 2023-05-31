<script setup>
import {useSabresStore} from "@/stores/sabres";
import router from "@/router";

// Définition des propriétés du composant
const props = defineProps(['id'])

// Récupération magasin des sabres
const storeSabre = useSabresStore()
// Récupère le tableau des sabres du magasin
const sabre = storeSabre.getSabreById(props.id)
</script>

<template>
  <main class="page-sabre">
    <div class="sabre">
      <h1>{{ sabre.nom }}</h1>

      <img :src="'/img/' + sabre.image" :alt="sabre.nom">
      <img :src="`/img/${sabre.image}`" :alt="sabre.nom">

      <p>{{ sabre.description }}</p>

      <ul class="details">
        <li>Prix: {{ sabre.prix }} CHF</li>
        <li v-if="sabre.stock < 11">Stock: {{ sabre.stock }} pièces</li>
        <li v-else>Stock: Plus de 10 pièces</li>
        <li>Longueur: {{ sabre.longueur }}cm</li>
        <li>Poids: {{ sabre.poids }} kg</li>
      </ul>
    </div>
  </main>
</template>

