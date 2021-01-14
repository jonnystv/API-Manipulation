<template lang="html">
  <div>
    <h1>Energy Use Chart</h1>
    <chart-data :chartData="energyUse.data.generationmix"></chart-data>
  </div>


</template>

<script>
import chartData from './components/chartData.vue'

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
  },

  components: {
    "chart-data": chartData
  }


};
</script>

<style>
</style>