<template>
  <div id="bar-chart">
  </div>
</template>

<script>
import * as echarts from 'echarts'
const option = {
  legend: {
    data: [
      {
        name: 'mac',
        icon: 'rect'
      },
      {
        name: 'windows',
        icon: 'rect'
      }
    ],
    orient: 'horizontal',
    top: 0,
    left: 36
    // ...
  },
  xAxis: {
    data: ['2022/6/4', '2022/6/5', '2022/6/6', '2022/6/7', '2022/6/8']
  },
  yAxis: {},
  series: [
    {
      type: 'bar',
      data: [23, 24, 18, 25, 27, 28, 25],
      barWidth: '20%',
      stack: 'x',
      name: 'mac',
    },
    {
      data: [5, 4, 3, 5, 10],
      type: 'bar',
      barWidth: '20%',
      stack: 'x',
      name: 'windows',
    }
  ],
  emphasis: {
      textStyle: {
          shadowBlur: 10,
          shadowColor: '#333'
      },
      label: {
        show: true,
        formatter: function(param) {
          console.log('params', param)
          return [param.name, `${param.seriesName}:{name|${param.data}}人`].join('\n');
        },
        position: 'top',
        rich: {
          name: {
            fontSize: 16,
            color: 'blue'
          }
        }
    }
  },
};
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  mounted() {
    var chart = echarts.init(document.getElementById('bar-chart'));
    chart.setOption(option);
  }
}
</script>

<style scoped>
#bar-chart {
  width: 600px;
  height: 400px;
}
</style>
