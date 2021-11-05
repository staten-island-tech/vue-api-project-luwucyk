<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div> {{characters}}</div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() {
    return {
      characters: [],
    };
  },
  created: function () {
    this.fetchData
  },
  methods: {
    fetchData: async function() {
      try {
        const response = await fetch("https://api.genshin.dev/characters/xiao/icon");
        const data = await response.json();
        this.characters = data.results;
      } catch (error) {
        console.log(error);
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
