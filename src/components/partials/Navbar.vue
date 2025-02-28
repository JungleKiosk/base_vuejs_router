<script>
import ColorMode from "./ColorMode.vue";

export default {
    name: "Navbar",
    components: {
    ColorMode
  },
};
</script>


<template>
    <nav class="navbar">
        <ul>
            <li><router-link to="/">{{ $t('navbar.home') }}</router-link></li>
            <li><router-link to="/about">{{ $t('navbar.aboutme') }}</router-link></li>
            <li><ColorMode></ColorMode></li>
        </ul>
    </nav>
</template>


<style>

</style>