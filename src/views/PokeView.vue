<script setup>
import { useGetData } from "@/composables/getData";
import { useRoute, useRouter } from "vue-router";
import { useFavoritesStore } from "@/store/favorites";

const route = useRoute();
const router = useRouter();
const useFavorites = useFavoritesStore();
const { add, findPoke } = useFavorites;

const { getData, data, loading, error } = useGetData();

const back = () => {
  router.push("/pokemons");
};

getData(`https://pokeapi.co/api/v2/pokemon/${route.params.name}`);
</script>

<template>
  <h1 v-if="loading">Loading ...</h1>
  <div class="alert alert-danger mt-2" v-if="error">Error: {{ error }}</div>
  <div v-if="data">
    <img :src="data.sprites?.front_default" alt="/" />
    <img :src="data.sprites?.back_default" alt="/" />
    <h1>Poke name: {{ $route.params.name }}</h1>
    <button
      class="btn btn-outline-primary"
      @click="add(data)"
      :disabled="findPoke(data.name)"
    >
      Add to Favorites
    </button>
  </div>

  <button class="btn btn-outline-primary mt-2" @click="back">go back</button>
</template>
