<template>
  <div class="character-card">
      <img class="character-img" v-bind:src="icon" alt="character icon">
      <h3 class="character-name">{{characters[0]}}</h3>
  </div>

</template>

<script>
export default {
  data() {
    return {
      characters: ["xiao"],
      icon: ["https://api.genshin.dev/characters/xiao/icon-big"],
    }
  },
created() {
    this.fetchData()
  },
  methods: {
    fetchData: async function() {
        try {
          const response = await fetch("https://api.genshin.dev/characters");
          const data = await response.json();
          console.log(data);
          this.characters = data
          
      } catch (error) {
          console.log('error');
      }
    },

  }

}
</script>

<style>
.character-card {
  background-color: rgb(26, 26, 29) ;
  display: flex;
  flex-direction: column;
  color: white;
  width: 15rem;
  height: 20rem;
  padding: 1rem;
  align-items: center;
  margin: 2rem;
  border-radius: 5%;
  overflow:hidden;
}

.character-img {
  height: 80%;
}
</style>