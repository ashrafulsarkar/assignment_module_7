<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue';
// import Chart from 'chart.js';
  
const chartCanvas = ref(null);
  
let myPieChart;
  
onMounted(() => {
    const data = {
        labels: ['Red', 'Blue', 'Yellow'],
        datasets: [{
        data: [300, 50, 100],
        backgroundColor: ['red', 'blue', 'yellow'],
        }],
    };

    const config = {
        type: 'pie',
        data: data,
    };

    myPieChart = new Chart(chartCanvas.value, config);

});
  
onBeforeUnmount(() => {
  if (myPieChart) {
    myPieChart.destroy();
    myPieChart = null;
  }
});

</script>

<template>
    <div class="mt-20">
        <h2 class="text-center text-4xl mt-6 mb-8">Pie Chart</h2>
        <div class="pie-chart">
            <canvas ref="chartCanvas" width="400" height="400"></canvas>
        </div>
    </div>
</template>
  
  
  
<style scoped>
.pie-chart {
    width: 450px;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100%;
    margin: auto;
}
</style>
  