<template>
  <div class="character-list">
      <div v-for="chara in charaList" :key="chara" v-bind:value="chara">
         <div class="character-card">
              <img :key="charaList.length" class="character-img" v-bind:src="icon[`${charaList.indexOf(`${chara}`)}`]" alt="character icon">
              <h3 class="character-name">{{chara}}</h3>

         </div>
        
      </div>
  </div>

</template>

<script>


export default {
  data() {
    return {
      charaList: [""],
      character: [""],
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
          console.log('error');
      }
      
      //character data info thingy idk my brain is falling apart?
      try {
        const response = await fetch(`https://api.genshin.dev/characters/${this.charaList[0]}`);
          const data = await response.json();
          this.character.push(data);
          

      } catch (error) {
          console.log(error);
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
  width: 5rem;
  height: 6rem;
  padding: 1.5rem;
  align-items: center;
  margin: 2rem;
  border-radius: 5%;
  
}

.character-img {
  height: 80%;
}

.character-name {
  text-transform: capitalize;
  margin-top: 0.5rem;
}

.character-list {
  display: flex;
  flex-direction: row;
  flex-wrap:wrap;
}
</style>