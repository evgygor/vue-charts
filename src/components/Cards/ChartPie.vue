<template>
  <CChartPie
    :datasets="defaultDatasets"
    :labels="['Passed', 'Failed']"
    :showLabel="false"
  />
</template>

<script>
import { CChartPie } from '@coreui/vue-chartjs'

export default {
  name: 'CChartPieExample',
  props: {
    chartData:{

    }
  },
  components: { CChartPie },
  computed: {
    defaultDatasets () {
      return [
        {
          backgroundColor: [
            '#41B883',
            '#E46651'
          ],
          data: this.chartData
        }
      ]
    }
  }
}
</script>