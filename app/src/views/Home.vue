<template>
  <div class="character-page">
    
    <h1>gesnin imapct charctrs</h1>
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
            
          });

          
          
      } catch (error) {
          alert(error);
      }
      
      //character data info thingy idk my brain is falling apart?
      

console.log(this.character);
    },
  }
}
</script>

<style >
html {
  background-image: url(https://d2ofqe7l47306o.cloudfront.net/games/1920x1200/genshin-impact-ps5-key-art.jpg);
  background-size: 110%;
  color:rgb(255, 255, 255)

}

.character-page {
  display: flex;
  flex-direction: column;
  align-items: center;
  background-image: linear-gradient(rgba(17, 13, 102, 0.521),rgba(9, 85, 104, 0.582)) ;

}

.character-list {
  display: flex;
  flex-direction: row;
  flex-wrap:wrap;
  justify-content: center;
  
}

.character-card {
  background-color: rgba(11, 11, 128, 0.555) ;
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