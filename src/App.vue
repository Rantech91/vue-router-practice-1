<script setup>
import { RouterLink, RouterView } from "vue-router";
import HelloWorld from "./components/HelloWorld.vue";
</script>

<template>
  <nav class="navbar navbar-light bg-light">
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
          class="btn btn-outline-primary"
          to="/pokemons"
          >Pokemons</RouterLink
        >
      </div>
    </div>
  </nav>
  <div class="container">
    <RouterView />
  </div>
</template>
