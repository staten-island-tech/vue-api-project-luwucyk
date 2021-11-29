<template>
  <div>
    <router-link class="link" to="/">Home</router-link>
    <router-view/>
      
  </div>
  
</template>

<script>
/* import Home from "@/views/Home.vue"
import About from "@/views/About.vue" */
export default {
components: {
   /*  Home, About */
  },
  }
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300&display=swap');

html, body {
  font-family: 'Roboto', sans-serif;
}

.link {
  color: rgb(0, 255, 255);
  margin: 1rem;
  font: bold;
}

.link:active {
  color: white;
}

</style>