<template>
  <div class="character-list">
      <div  :key="charaList.length" v-bind:value="charaList">
         <div class="character-card">
              <img :key="charaList.length" class="character-img" alt="character icon">
              <h3 class="character-name">{{charaList}}</h3>

         </div>
        
      </div>
  </div>

</template>

<script>


export default {
   props: {
   charaList: {
   },
   icon: {
   } 
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