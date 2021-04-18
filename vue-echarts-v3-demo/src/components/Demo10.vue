<template>
  <div class="echarts">
    <h2><router-link to="/">Go Back</router-link></h2>
    <IEcharts :option="line" @ready="onReady" @click="onClick"></IEcharts>
  </div>
</template>

<script>
import IEcharts from 'vue-echarts-v3/src/lite.js'
import 'echarts/lib/component/title' // 引入标题组件
import 'echarts/lib/chart/line'
export default {
  name: 'Demo10',
  components: {IEcharts},
  data: () => ({
    line: {
      title: {
        text: 'ECharts Line Demo'
      },
      tooltip: {},
      xAxis: {
        type: 'category',
        data: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun']
      },
      yAxis: {
        type: 'value'
      },
      series: [{
        type: 'line',
        data: [
          150, 230, 224, 218, 135, 147, 260
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
