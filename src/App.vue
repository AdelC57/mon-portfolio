<script setup>
import { RouterView } from "vue-router";
import Header from "./components/Header.vue";
</script>

<template>
  <header>
    <Header />
  </header>
  <router-view />
  <footer></footer>
</template>

<style scoped></style>



