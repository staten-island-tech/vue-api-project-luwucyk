<template>
  <div class="info-page">
    <div class="character-details">
      <div class="name-el txtbox">
        <h4>{{character.name}}</h4> 
        <span class="elem-icon" v-bind:src="character.vision" alt="element">{{character.vision}}</span>
       <p class="details-text">Affiliation: {{character.affiliation}}</p>
      </div>

    <div class="character-stats">

      <div class="txtbox constellations">
      <h4>Constellations:</h4>
      <div class="" v-for="stell in character.constellations" :key="stell.length" v-bind:value="character.constellations">
        <p class="details-text cons-name title">{{stell.unlock}}: {{stell.name}}</p>
        <p class="details-text cons-desc">{{stell.description}}</p>
      </div>
      </div>

      <div class="txtbox talents">
      <h4>Talents:</h4>
      <div class="" v-for="talent in character.skillTalents" :key="talent.length" v-bind:value="character.skillTalents">
        <p class="details-text talent-name title">{{talent.name}}</p>
        <p class="details-text talent-desc">{{talent.description}}</p>
       
      </div>
       <img class="bg-img" :key="character" v-bind:src="bg" alt="character splash art">
      </div>


    </div>

    </div>

    <img class="card" :key="character.length" v-bind:src="img" alt="character icon">
  </div>
</template>

<script>
export default {
  data() {
    return {
      character: [`${this.chr}`],
      img: [],
      bg: [],
    }
  },
  created() {
    this.fetchData()
  },
  props: ['chr'],
  methods: {
    fetchData: async function() {

      //icon mcchangerino - charalist is megalist of all charas, then foreach?
        try {
          this.img = `https://api.genshin.dev/characters/${this.character}/card` ;
          this.bg = `https://api.genshin.dev/characters/${this.character}/gacha-splash` ;
          const response = await fetch(`https://api.genshin.dev/characters/${this.character}`);
          const data = await response.json();
          this.character = data;
 
          console.log(this.character);         
          
      } catch (error) {
          alert(error);
      }
}
  }}
</script>

<style scoped>
h4 {
  color: rgb(66, 233, 255);
  margin: 0rem auto;
  size: 2%;
  text-transform: uppercase;

}

.bg-img {
  position: fixed;
  top: 5%;
  right: 15rem;
  transform: scale(1.5);
  z-index: -1;
  opacity: 1;
}

.title {
  color: rgb(208, 182, 255);
}

.character-stats {
  display: flex;
  flex-direction: row;
}

.constellations {
  width: 40%;
}

.talents {
  width: 60%;
  overflow: hidden;
}

.txtbox {
 margin-bottom: 2rem;
 margin-right: 2rem;
 background-color: rgba(11, 11, 56, 0.747);
 padding: 1rem;
 overflow: hidden;
 height: 70%;
}

.name-el {

 display: flex;
 flex-direction: column;
 width: 25%;
}

.card {
  width: 25%;

}

.info-page {
  padding: 2rem;
  display: flex;
  align-items: flex-start;
background-image: linear-gradient(rgba(17, 13, 102, 0.521),rgba(9, 85, 104, 0.582)) ;
overflow: hidden;
}

.character-details {
 margin-right: 2rem;
 margin-left: 2rem;
 width: 70%;
 height: 25%;
 overflow: hidden;
 
}

</style>
