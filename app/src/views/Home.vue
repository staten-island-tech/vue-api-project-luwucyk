<template>
  <div>
    <card/>
  </div>
</template>

<script>
import card from "@/components/card.vue"
export default {
data() {
    return {
      charaList: [""],
      character: [""],
      icon: [],
 
    }
  },
components: {
    card,
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

</style>