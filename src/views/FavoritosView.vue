<script setup>
import { useFavoritesStore } from "@/store/favorites";
import { storeToRefs } from "pinia";
import { RouterLink } from "vue-router";

const useFavorites = useFavoritesStore();
const { favorites } = storeToRefs(useFavorites);
const { remove } = useFavorites;
</script>

<template>
  <h1>Favorite Pokemons</h1>
  <p v-if="favorites.length === 0">No favorite Pokemons</p>
  <ul class="list-group" v-else>
    <li class="list-group-item" v-for="poke in favorites" :key="poke.id">
      <div>
        {{ poke.name }}
      </div>
      <div>
        <RouterLink
          :to="`/pokemons/${poke.name}`"
          class="btn btn-primary btn-sm me-2"
        >
          See more
        </RouterLink>
        <button class="btn btn-danger btn-sm" @click="remove(poke.id)">
          Eliminar
        </button>
      </div>
    </li>
  </ul>
</template>
