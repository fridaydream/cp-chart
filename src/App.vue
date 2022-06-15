<template>
  <div>
    <div id='main'></div>
    <line-chart />
    <bar-chart />
    <circle-chart />
  </div>
</template>

<script>
/* eslint-disable no-debugger */

import * as echarts from 'echarts'
import 'echarts-wordcloud';
import LineChart from './LineChart'
import BarChart from './BarChart'
import CircleChart from './CircleChart'

export default {
  name: 'App',
  components: {
    LineChart,
    BarChart,
    CircleChart,
  },
  mounted() {
    var chart = echarts.init(document.getElementById('main'));
    var option = {
                tooltip: {},
                series: [ {
                    type: 'wordCloud',
                    gridSize: 2,
                    sizeRange: [12, 50],
                    rotationRange: [0, 90],
                    shape: 'square',
                    width: 600,
                    height: 400,
                    drawOutOfBound: true,
                    textStyle: {
                        color: function () {
                            return 'rgb(' + [
                                Math.round(Math.random() * 160),
                                Math.round(Math.random() * 160),
                                Math.round(Math.random() * 160)
                            ].join(',') + ')';
                        }
                    },
                    emphasis: {
                        textStyle: {
                            shadowBlur: 10,
                            shadowColor: '#333'
                        }
                    },
                    
                    data: [
                        {
                            name: 'Sam S Club',
                            value: 10000,
                            kess: 11,
                            textStyle: {
                                color: 'black'
                            },
                            // emphasis: {
                            //     textStyle: {
                            //         color: 'red'
                            //     }
                            // }
                        },
                        {
                            name: 'Macys',
                            value: 6181
                        },
                        {
                            name: 'Amy Schumer',
                            value: 4386
                        },
                        {
                            name: 'Jurassic World',
                            value: 4055
                        },
                        {
                            name: 'Charter Communications',
                            value: 2467
                        },
                        {
                            name: 'Chick Fil A',
                            value: 2244
                        },
                        {
                            name: 'Planet Fitness',
                            value: 1898
                        },
                        {
                            name: 'Pitch Perfect',
                            value: 1484
                        },
                        {
                            name: 'Express',
                            value: 1112
                        },
                        {
                            name: 'Home',
                            value: 965
                        },
                        {
                            name: 'Johnny Depp',
                            value: 847
                        },
                        {
                            name: 'Lena Dunham',
                            value: 582
                        },
                        {
                            name: 'Lewis Hamilton',
                            value: 555
                        },
                        {
                            name: 'KXAN',
                            value: 550
                        },
                        {
                            name: 'Mary Ellen Mark',
                            value: 462
                        },
                        {
                            name: 'Farrah Abraham',
                            value: 366
                        },
                        {
                            name: 'Rita Ora',
                            value: 360
                        },
                        {
                            name: 'Serena Williams',
                            value: 282
                        },
                        {
                            name: 'NCAA baseball tournament',
                            value: 273
                        },
                        {
                            name: 'Point Break',
                            value: 265
                        }
                    ]
                } ]
            };
    chart.setOption(option);
            // 关键代码
    chart.on('click', (param) => {
      // eslint-disable-next-line
      console.log(param);
    });

  }
}
</script>

<style>
#main {
  width: 600px;
  height: 400px;
}
</style>
