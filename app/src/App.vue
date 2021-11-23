<template>
  <div>
    <router-link class="link" to="/about">about</router-link> |
    <router-link class="link" to="/">home</router-link>
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

.link {
  color: rgb(219, 255, 14);
}

.link:active {
  color: white;
}

</style>