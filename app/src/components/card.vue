<template>
  <div class="character-card">
      <span>{{characters[0]}}</span>
      <img class="character-img" src="https://api.genshin.dev/characters/xiao/icon-big" alt="character icon">
      <h3 class="character-name">idjfskbkbnsg</h3>
  </div>

</template>

<script>
export default {
  data() {
    return {
      characters: ["xiao"],
      icon: [],
    }
  },
created() {
    this.birth()
  },
  methods: {
    birth: function() {
      console.log('humu');
      this.characters = ['albedo'];

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
  width: 15rem;
  height: 20rem;
  padding: 1rem;
  align-items: center;
  margin: 2rem;
  border-radius: 5%;
  overflow:hidden;
}

.character-img {
  height: 80%;
}
</style>