<script>
import { Bar, mixins } from 'vue-chartjs'
const { reactiveProp } = mixins

export default {
  extends: Bar,
  mixins: [reactiveProp],
  props: {
    chartData: {
      type: Object,
      default: null
    },
    options: {
      type: Object,
      default: null
    }
  },
  watch: {
    options () {
      this.renderChart(this.chartData, this.options)
    }
  },
  mounted () {
    console.log('render')
    this.renderChart(this.chartData, this.options)
  },
  methods: {
    test () {
      var index = 0
      var ci = this.$data._chart
      var meta = ci.getDatasetMeta(index)

      // See controller.isDatasetVisible comment
      meta.hidden = meta.hidden === null ? !ci.data.datasets[index].hidden : null

      // We hid a dataset ... rerender the chart
      ci.update()
    }
  }
}
</script>
