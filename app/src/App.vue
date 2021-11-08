<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link> |
      <span>{{characters}}</span>
    </div>
    <router-view/>
  </div>
</template>

<script>

export default {
   data() {
    return {
      characters: ["bruh"],
    };
  },
  created: function () {
    this.fetchData,
    this.bruh
  },
  methods: {
    fetchData: async function() {
      try {
        const response = await fetch("https://api.genshin.dev/characters");
        const data = await response.json();
        this.characters = data.results;
        console.log(this.characters);
        console.log("hi");
      } catch (error) {
        console.log(error);
      }
    },
    bruh: function() {
      console.log("bruh");
    }
  }
}
</script>


<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
