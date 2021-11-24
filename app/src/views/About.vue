<template>
  <div class="info-page">
    <div class="character-details">
      <div class="name-el">
        <h4 class="title" >{{character.name}}</h4> 
        <img class="elem-icon" src="https://api.genshin.dev/elements/anemo/icon" alt="element icon">
      </div>
       
      <div class="aff">Affiliation: {{character.affiliation}}</div>
      
    </div>
    <img class="card" :key="character.length" v-bind:src="img" alt="character icon">
  </div>
</template>

<script>
export default {
  data() {
    return {
      character: [`xiao`],
      img: [],
    }
  },
  created() {
    this.fetchData()
  },
  methods: {
    fetchData: async function() {

      //icon mcchangerino - charalist is megalist of all charas, then foreach?
        try {
          const response = await fetch(`https://api.genshin.dev/characters/xiao`);
          const data = await response.json();
          this.character = data;
          this.img = `https://api.genshin.dev/characters/xiao/card` ; 
          console.log(this.character);         
          
      } catch (error) {
          console.log('error');
      }
}
  }}
</script>

<style scoped>
h4 {
  color: white;
  margin: 0rem auto;
  size: 2%;
  text-transform: uppercase;

}

.elem-icon {
  width: 2rem;
  position: relative;
  left: 8rem;
  bottom: 1rem;
}

.name-el {
  height: 2rem;
}

.card {
  width: 50%;
}

.info-page {
  margin: 2rem;
  display: flex;
  align-items: flex-start;


}

.character-details {
 background-color: rgb(26, 26, 29);
 margin-right: 2rem;
 padding: 1rem;
 display: flex;
 flex-direction: column;
 width: 25%;
 height: 25%;
 overflow: hidden;
}

</style>
