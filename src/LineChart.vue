<template>
  <div id="line-chart">
  </div>
</template>

<script>
import * as echarts from 'echarts'
const option = {
  xAxis: {
    type: 'category',
    data: ['1时', '2时', '3时']
  },
  yAxis: {
    type: 'value'
  },
  series: [
    {
      data: [120, 200, 150],
      type: 'line',
      smooth: true,
      tooltip: {},
      emphasis: {
          textStyle: {
              shadowBlur: 10,
              shadowColor: '#333'
          },
          label: {
            show: true,
            formatter: function(param) {
              return [param.name, `在线{name|${param.data}}人`].join('\n');
            },
            rich: {
              name: {
                fontSize: 16,
                color: 'blue'
              }
            }
        }
      },
    }
  ]
};
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  mounted() {
    var chart = echarts.init(document.getElementById('line-chart'));
    chart.setOption(option);
  }
}
</script>

<style scoped>
#line-chart {
  width: 600px;
  height: 400px;
}
</style>
