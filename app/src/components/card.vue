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
  props: {
   ['charaList'],
   ['icon']  
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