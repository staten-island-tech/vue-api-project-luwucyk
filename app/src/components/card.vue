<template>
  <div class="character-list">
      <div v-for="chara in cardDetail.charaList" :key="chara" v-bind:value="chara">
         <div class="character-card">
              <img :key="cardDetail.charaList.length" class="character-img" v-bind:src="cardDetail.icon[`${cardDetail.charaList.indexOf(`${chara}`)}`]" alt="character icon">
              <h3 class="character-name">{{chara}}</h3>

         </div>
        
      </div>
  </div>

</template>

<script>


export default {
  /* props: {
   charaList: {
     type: Array
   },
   icon: {
     type: Array
   } 
  }*/
  data() {
    return {
      cardDetail: {
        charaList: [],
        character: [],
        icon: [],
        }
 
    }
  },
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