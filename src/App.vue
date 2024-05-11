<template>
  <TheHeader />
  <main class="main-container">
  </main>
  <TheNav />
</template>

<script setup>
import TheHeader from "./components/TheHeader.vue";
import TheNav from "./components/TheNav.vue";


</script>

<style lang="scss" scoped>
* {
  all: initial;
}

.main-container {
  display: flex;
  flex-grow: 1;
  flex-direction: column;
}
</style>