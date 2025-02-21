<script>
import Navbar from "./components/partials/Navbar.vue";


export default {
  components: {
    Navbar
  },
};
</script>

<template>
  <div id="app">
    <Navbar />
    <router-view />
  </div>
</template>

<style>
</style>