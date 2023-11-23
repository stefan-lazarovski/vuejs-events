<script setup>
import { RouterLink, RouterView } from 'vue-router'
import Header from './components/Header.vue'
</script>

<template>
  <div id="layout">
    <Header />
    <RouterView />
  </div>
</template>

<style lang="scss">
#layout {
  // font-family: var(--font-black);
}
</style>
