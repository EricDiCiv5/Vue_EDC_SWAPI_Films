<template>
  <HeaderSwapi />
  <Card :pelis="pelicules" />
  <FooterSwapi />
</template>

<script setup>
import HeaderSwapi from "./components/HeaderSwapi.vue";
import Card from "./components/Card.vue";
import FooterSwapi from "./components/FooterSwapi.vue";

import { ref } from "vue";

const pelicules = ref([]);

/*----FUNCIÓ PER COMUNICAR AMB API I VEURE PELICULES----*/

const api_Url = "https://swapi.dev/api/films/";

const mostrar_Pelicules = async () => {
  const response = await fetch(api_Url);
  const data = await response.json();
  pelicules.value.push(data.results);

  if (!response.ok) {
    throw new Error(`fetch error! status: ${response.status}`);
  }
};

mostrar_Pelicules();
</script>

<style>
@font-face {
  font-family: "StarWars";
  src: url("./star_jedi/starjedi/Starjedi.ttf");
}

@font-face {
  font-family: "StarWars2";
  src: url("./star_jedi/starjedi/Starjhol.ttf");
}
</style>
