<template>
  <div id="app">
    <Header />
    <main style="margin-top: 80px;">
      <!-- Nanti konten dari section hero, fitur, dst -->
      <router-view />
    </main>
  </div>
</template>

<script>
import Header from "./components/Header.vue";

export default {
  components: {
    Header,
  },
};
</script>

<style>
body {
  margin: 0;
  font-family: 'Poppins', sans-serif;
}
</style>
