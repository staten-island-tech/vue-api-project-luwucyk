<template>
  <div class="info-page">
    <div class="character-details">
      <span>Name</span>
      <div class="rarity">rarity, use star values?</div>
      <img src="https://api.genshin.dev/elements/anemo/icon" alt="element icon">

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
h1{
  color: white;
}

.info-page {
  margin: 2rem;
  display: flex;

}

.character-details {
 background-color: rgb(26, 26, 29);
 margin: 2rem;
 padding: 1rem;
 display: flex;
 flex-direction: column;
 width: 25%;
}

</style>
