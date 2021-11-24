<template>
  <div class="info-page">
    <div class="character-details">
      <div class="name-el">
        <h4 class="title" >{{character.name}}</h4> 
        <span class="elem-icon" v-bind:src="character.vision" alt="element">{{character.vision}}</span>
      </div>
      <div class="aff">Affiliation: {{character.affiliation}}</div>
    </div>
    <div class="character-stats">
      <div class="constellations"></div>
    </div>
    <img class="card" :key="character.length" v-bind:src="img" alt="character icon">
  </div>
</template>

<script>
export default {
  data() {
    return {
      character: [`kokomi`],
      img: [],
      elIcon:{Anemo: `https://api.genshin.dev/elements/anemo/icon`,
      Geo: `https://api.genshin.dev/elements/geo/icon`, },
    }
  },
  created() {
    this.fetchData()
  },
  methods: {
    fetchData: async function() {

      //icon mcchangerino - charalist is megalist of all charas, then foreach?
        try {
          this.img = `https://api.genshin.dev/characters/${this.character}/card` ;
          const response = await fetch(`https://api.genshin.dev/characters/${this.character}`);
          const data = await response.json();
          this.character = data;
/*           const elem = this.character.vision;
          this.elIcon = `https://api.genshin.dev/elements/${elem}/icon` */
 
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

.name-el {
  height: 2rem;
  margin-bottom: 1.5rem;
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
