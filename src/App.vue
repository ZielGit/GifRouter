<script>
import { RouterView } from 'vue-router';
import Navbar from './components/Navbar.vue';

export default {
  components: {
    RouterView, Navbar
  }
};
</script>

<template>
  <Navbar />

  <div class="container mt-3 border">
    <RouterView />
  </div>
</template>
