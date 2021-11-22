<template>
  <div>
    <router-link :to="{name: 'About'}">hihihihihi</router-link>
      <Home/>
  </div>
  
</template>

<script>
import Home from "@/views/Home.vue"
export default {
components: {
    Home,
  },
  }
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300&display=swap');

html, body {
  font-family: 'Roboto', sans-serif;
}

</style>