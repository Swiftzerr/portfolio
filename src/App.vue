<script setup>
import { RouterLink, RouterView } from "vue-router";
</script>

<template>
  <div class="wrapper">
    <nav class="navbar" :style="{ height: scroll > 0 ? '3em' : '4em' }">
      <RouterLink class="router-item" to="/">Home</RouterLink>
    </nav>
    <RouterView />
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      scroll: window.pageYOffset,
    };
  },
  created() {
    window.addEventListener("scroll", () => {
      this.scroll = window.pageYOffset;
    });
  },
};
</script>
