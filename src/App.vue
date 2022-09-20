<script setup>
import Navbar from './components/Navbar.vue'
// import TheWelcome from './components/TheWelcome.vue'
import Home from "./components/Home.vue"
</script>

<template>
  <header>
    <Navbar />
  </header>

  <main>
    <Home />
  </main>
</template>

<style scoped>
header {
  top: 0;
  width: 100%;
  padding: 0 50px;
  font-family: 'SF Mono', sans-serif;
}
</style>
