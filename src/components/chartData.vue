<template>

  <div>
      <GChart
        v-if="createDataTableData"
        type="PieChart"
        :data="createDataTableData"
        />
      <h1>Chart Data Component</h1>

  </div>
</template>

<script>
import { GChart } from 'vue-google-charts'

export default {
    name: "chart-data",
    props: ['chartData'],
    data(){
        return { chartDataTable: [
            ['Fuel', 'Percentage']]
        }
    },

    computed: {
        createDataTableData(){
          

          for (let energyObject of this.chartData) {
            let objectArray = [];
              for (let keyValue in energyObject) {
                  objectArray.push(keyValue);
                  this.chartDataTable.push(objectArray);
              }
              
          } 
        }
    },

    mounted(){
        this.createDataTableData();
        console.log(chartData);
        
    },

    components: {
        GChart
    }

}
</script>

<style>

</style>