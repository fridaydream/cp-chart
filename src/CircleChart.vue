<template>
  <div id="circle-chart">
  </div>
</template>

<script>
import * as echarts from 'echarts'
const option = {
  title: {
    text: `使用时间(人均)\n8小时\n应用总数\n8`,
    left: 'center',
    top: 'center'
  },
  series: [
    {
      type: 'pie',
      data: [
        {
          value: 335,
          name: 'A'
        },
        {
          value: 234,
          name: 'B'
        },
        {
          value: 1548,
          name: 'C'
        }
      ],
      radius: ['40%', '70%']
    }
  ]
};
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  mounted() {
    var chart = echarts.init(document.getElementById('circle-chart'));
    chart.setOption(option);
  }
}
</script>

<style scoped>
#circle-chart {
  width: 600px;
  height: 400px;
}
</style>
