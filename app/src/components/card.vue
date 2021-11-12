<template>
  <div  class="character-card">
      <img :key="charaList.length" class="character-img" v-bind:src="icon" alt="character icon">
      <h3 class="character-name">{{characters[0].name}}</h3>
  </div>

</template>

<script>
export default {
  data() {
    return {
      charaList: [""],
      characters: [""],
      icon: [""],
    }
  },
created() {
    this.fetchData()
  },
  methods: {
    fetchData: async function() {
        try {
          const response = await fetch('https://api.genshin.dev/characters');
          const data = await response.json();
          this.charaList = data;
          this.icon = `https://api.genshin.dev/characters/${this.charaList[0]}/icon-big`
          
      } catch (error) {
          console.log('error');
      }
      
      try {
        const response = await fetch(`https://api.genshin.dev/characters/${this.charaList[0]}`);
          const data = await response.json();
          this.characters.push(data);
          

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
  
}

.character-img {
  height: 80%;
}
</style>