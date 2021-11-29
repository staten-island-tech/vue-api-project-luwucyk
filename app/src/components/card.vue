<template>
<div>
      <div :key="charaList.length" v-bind:value="charaList">
         <router-link :to="{name: 'info' ,params: {chr:`${charaList}`}}" class="character-card">
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


.character-img {
  height: 80%;
}

.character-name {
  text-transform: capitalize;
  margin-top: 0.5rem;
  opacity: .7;
}

</style>