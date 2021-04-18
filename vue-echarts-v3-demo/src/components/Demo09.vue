<template>
  <div class="echarts">
    <h2><router-link to="/">Go Back</router-link></h2>
    <IEcharts :option="gauge" @ready="onReady" @click="onClick"></IEcharts>
  </div>
</template>

<script>
import IEcharts from 'vue-echarts-v3/src/lite.js'
import 'echarts/lib/component/title' // 引入标题组件
import 'echarts/lib/chart/gauge'
export default {
  name: 'Demo09',
  components: {IEcharts},
  data: () => ({
    gauge: {
      title: {
        text: 'ECharts Gauge Demo'
      },
      tooltip: {},
      series: [{
        type: 'gauge',
        data: [
          {value: 70}
        ]
      }]
    }
  }),
  methods: {
    onReady (instance) {
      console.log(instance)
    },
    onClick (event, instance, echarts) {
      console.log(arguments)
    }
  }
}
</script>
<style scoped>
  .echarts{
    width: 400px;
    height: 400px;
    margin: auto;
    text-align: center;
  }
</style>
