<template>
  <div class="character-page">
    
    <h2>gesnin imapct charctr</h2>
      <div class="character-list">
        
           <card v-for="chara in charaList" :key="chara" v-bind:value="chara" :charaList=chara :icon="icon[`${charaList.indexOf(`${chara}`)}`]" /> 
         <!-- <div class="character-card">
              <img :key="charaList.length" class="character-img" v-bind:src="icon[`${charaList.indexOf(`${chara}`)}`]" alt="character icon">
              <h3 class="character-name">{{chara}}</h3>

         </div> -->
        
      </div>

  
  </div>

</template>

<script>

import card from "@/components/card.vue"


export default {
  components: {
    card,
  },
  data() {
    return {
      charaList: [],
      character: [],
      icon: [],
    }
  },
  created() {
    this.fetchData()
  },
  methods: {
    fetchData: async function() {

      //icon mcchangerino - charalist is megalist of all charas, then foreach?
        try {
          const response = await fetch('https://api.genshin.dev/characters');
          const data = await response.json();
          this.charaList = data;
          
          this.charaList.forEach(element => {
              this.icon.push(`https://api.genshin.dev/characters/${element}/icon`) ;
              this.character.push(`https://api.genshin.dev/characters/${element}`) ;
            
          });

          
          
      } catch (error) {
          console.log('error');
      }
      
      //character data info thingy idk my brain is falling apart?
      

console.log(this.character);
    },
  }
}
</script>

<style>
html {
  background-color: black;
  color:white

}

.character-page {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.character-list {
  display: flex;
  flex-direction: row;
  flex-wrap:wrap;
  justify-content: center;
  
}

.character-card {
  background-color: rgb(26, 26, 29) ;
  display: flex;
  flex-direction: column;
  color: white;
  width: 5rem;
  height: 6rem;
  padding: 1.5rem;
  align-items: center;
  margin: 2rem;
  border-radius: 5%;
  overflow: hidden;
  
}

.character-img {
  height: 80%;
}

.character-name {
  text-transform: capitalize;
  margin-top: 0.5rem;
}

</style>