<script setup>
import { RouterLink, RouterView } from "vue-router";
import HelloWorld from "./components/HelloWorld.vue";
</script>

<template>
  <nav class="navbar navbar-dark bg-dark">
    <div class="container">
      <RouterLink class="navbar-brand" to="/">
        <img
          src="@/assets/logo.svg"
          alt=""
          width="30"
          height="24"
          class="d-inline-block align-text-top"
        />
        PokeApp
      </RouterLink>
      <div>
        <RouterLink
          active-class="active"
          class="btn btn-outline-primary me-2"
          to="/"
          >Home</RouterLink
        >
        <RouterLink
          active-class="active"
          class="btn btn-outline-primary me-2"
          to="/pokemons"
          >Pokemons</RouterLink
        >

        <RouterLink
          to="/favorites"
          class="btn btn-outline-primary bg-light"
          active-class="active"
        >
          Favorites
        </RouterLink>
      </div>
    </div>
  </nav>
  <div class="container text-center">
    <RouterView />
  </div>
</template>
