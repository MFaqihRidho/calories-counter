<script setup>
import { RouterLink, RouterView } from 'vue-router'
import navbar from './components/navbar.vue';
import Layout from './components/Layout.vue'
</script>

<template>
  <div class="font-Poppins">
    <navbar></navbar>
    <RouterView />
  </div>
</template>

<style scoped>
.active {
  color: white;
}
</style>