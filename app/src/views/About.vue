<template>
  <div>
    <h1>dhfsgdshfkjhgkjdfng</h1>
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

.character-details {
 background-color: red;
}

</style>
