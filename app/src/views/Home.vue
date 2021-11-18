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
      charaList: [],
      character: [],
      icon: [],
 
    }
  },
components: {
    card,
  },


}
</script>

<style>

</style>