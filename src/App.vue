<template lang="html">
  <div>
    
  </div>


</template>

<script>
export default {
  name: "app",
  data(){
    return {
      energyUse: []
    }
  },
  mounted(){
    fetch("https://api.carbonintensity.org.uk/generation")
    .then(res => res.json())
    .then(energyUseAPI => this.energyUse = energyUseAPI)
  }


};
</script>

<style>
</style>