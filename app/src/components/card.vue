<template>
<div>
      <div :key="charaList.length" v-bind:value="charaList">
         <router-link :to="{name: 'info' ,params: {name:`${charaList}`}}" class="character-card">
              <img :key="charaList.length" class="character-img" v-bind:src="icon" alt="character icon">
              <h3 class="character-name">{{charaList}}</h3>

         </router-link>
        
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

<style scoped>
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

</style>