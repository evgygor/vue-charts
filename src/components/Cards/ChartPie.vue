<template>
  <CChartPie
    :datasets="defaultDatasets"
    :labels="['Passed', 'Failed']"
  />
</template>

<script>
import { CChartPie } from '@coreui/vue-chartjs'

export default {
  name: 'CChartPieExample',
  props: {
    chartTimeWindow: {
      type: String,
      default: "1", // 3 | 6 | 24
    },
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
          data: [40, 20]
        }
      ]
    }
  }
}
</script>