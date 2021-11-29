<template>
  <div>
    <router-link class="link" to="/">home</router-link>
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
  color: rgb(255, 213, 27);
}

.link:active {
  color: white;
}

</style>