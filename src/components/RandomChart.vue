<template>
  <div class="small">
    <box-plot-chart :chart-data="datacollection" />
    <button @click="fillData();">Randomize</button>
  </div>
</template>

<script>
import BoxPlotChart from "./BoxPlotChart.js";

export default {
  components: {
    BoxPlotChart
  },
  data() {
    return {
      datacollection: null
    };
  },
  mounted() {
    this.fillData();
  },
  methods: {
    fillData() {
      this.datacollection = {
        labels: [this.getRandomInt(), this.getRandomInt()],
        datasets: [
          {
            label: "Data One",
            backgroundColor: "#f87979",
            data: [this.getRandomValues(100, 200), this.getRandomValues()]
          },
          {
            label: "Data One",
            backgroundColor: "blue",
            data: [this.getRandomValues(), this.getRandomValues(20, 80)]
          }
        ]
      };
    },
    getRandomInt() {
      return Math.floor(Math.random() * (50 - 5 + 1)) + 5;
    },
    getRandomValues(min = 0, max = 100) {
      return Array.from({ length: 100 }).map(
        () => Math.random() * (max - min) + min
      );
    }
  }
};
</script>

<style>
.small {
  max-width: 600px;
  margin: 150px auto;
}
</style>
