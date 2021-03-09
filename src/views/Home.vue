<template>
  <div class="container">
    <bar-chart ref="testchart"
      :chartData="chartdata"
      :options="options"/>
      <button @click="test">Test</button>
  </div>
</template>

<script>
import BarChart from './chart/Bar.vue'

export default {
  name: 'BarChartContainer',
  components: {
    'bar-chart': BarChart
  },
  data: () => ({
    loaded: false,
    chartdata: null,
    options: null
  }),
  async mounted () {
    this.chartdata = {
      labels: ['Red', 'Blue', 'Yellow', 'Green', 'Purple', 'Orange'],
      datasets: [{
        label: '# of Votes',
        data: [12, 19, 3, 5, 2, 3],
        backgroundColor: [
          'rgba(255, 99, 132, 0.2)',
          'rgba(54, 162, 235, 0.2)',
          'rgba(255, 206, 86, 0.2)',
          'rgba(75, 192, 192, 0.2)',
          'rgba(153, 102, 255, 0.2)',
          'rgba(255, 159, 64, 0.2)'
        ],
        borderColor: [
          'rgba(255, 99, 132, 1)',
          'rgba(54, 162, 235, 1)',
          'rgba(255, 206, 86, 1)',
          'rgba(75, 192, 192, 1)',
          'rgba(153, 102, 255, 1)',
          'rgba(255, 159, 64, 1)'
        ],
        borderWidth: 1
      }]
    }
  },
  methods: {
    test () {
      // this.options = {
      //   legend: {
      //     display: true,
      //     labels: {
      //       onClick: function (e, legendItem) {
      //         console.log(e)
      //         var index = legendItem.datasetIndex
      //         var ci = this.chart
      //         var meta = ci.getDatasetMeta(index)

      //         // See controller.isDatasetVisible comment
      //         meta.hidden = meta.hidden === null ? !ci.data.datasets[index].hidden : null

      //         // We hid a dataset ... rerender the chart
      //         ci.update()
      //       }
      //     }
      //   }
      // }
      // console.log('test')
      this.$refs.testchart.test()
    }
  }
}
</script>
