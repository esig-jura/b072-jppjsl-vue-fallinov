<script setup>
import SabreLaser from "@/components/SabreLaser.vue";
import {useSabresStore} from "@/stores/sabres";

// Récupération magasin des sabres
const storeSabre = useSabresStore()
// Récupère le tableau des sabres du magasin
const sabres = storeSabre.getSabresAZ

</script>
<template>
  <main class="page-accueil">
    <h1>Découvrez nos sabres <strong>LASER</strong></h1>

    <ul class="sabres">
      <SabreLaser
        v-for="sabre in sabres"
        :key="sabre.id"
        :sabre="sabre"
      />
    </ul>
  </main>
</template>

