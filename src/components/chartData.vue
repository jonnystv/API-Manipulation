<template>
  <div>

      <h1>Chart Data Component</h1>

  </div>
</template>

<script>
export default {
    name: "chart-data",
    props: ['chartData'],
    data(){
        return { chartDataTable: [
            ['Fuel', 'Percentage']]
        }
    },

    methods: {
        createDataTableData(){
          
          for(energyObject in this.chartData) {
            const objectArray = [];
              for(keyValue of energyObject) {
                  objectArray.push(keyValue);
                  chartDataTable.push(objectArray);
              }
              
          } 
        }

    },

    mounted(){
        createDataTableData();
        
    }
}
</script>

<style>

</style>