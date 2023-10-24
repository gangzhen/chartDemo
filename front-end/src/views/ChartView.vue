<template>

  <div>

    <el-card>

      <el-row type="flex" justify="center" align="middle">
        <el-col :span="14">
          <div style="height: 800px; text-align: center" id="charts01"></div>
        </el-col>
      </el-row>

      <el-row type="flex" justify="center" align="middle">
        <el-col :span="14">
          <div style="height: 800px; text-align: center" id="charts02"></div>
        </el-col>
      </el-row>

      <el-row type="flex" justify="center" align="middle">
        <el-col :span="14">
          <div style="height: 800px; text-align: center" id="charts03"></div>
        </el-col>
      </el-row>

      <el-row type="flex" justify="center" align="middle">
        <el-col :span="14">
          <div style="height: 800px; text-align: center" id="charts04"></div>
        </el-col>
      </el-row>

    </el-card>

  </div>

</template>

<script>

import * as echarts from 'echarts';

const chart01_X = [0, 100, 200, 300, 400, 500, 600, 700, 800, 900, 1000, 1100, 1200, 1300, 1400, 1500, 1600, 1700, 1800];
const chart01_Y01 = [4.45, 2.49, 4.76, 2.65, 3.75, 4.27, 1.73, 4.71, 2.92, 3.82, 4.38, 2.08, 4.92, 2.53, 3.49, 4.27, 2.49, 4.61, 4.83];
const chart01_Y02 = [4.42, 2.11, 4.74, 2.67, 2.28, 4.87, 3.17, 4.23, 3.6, 3.85, 5.12, 1.41, 4.98, 4.37, 2.97, 4.63, 2.51, 4.62, 4.82];
const chart02_X = [];
const chart02_Y = [];
const chart03_X = [];
const chart03_Y = [];
const chart04_X = [];
const chart04_Y = [];
const table01_Data = [];
const table02_Data = [];

const option01 = {
  title: {
    text: '基于EMG和IMU的动作识别的原始数据图',
    x: 'center',
  },
  tooltip: {
    trigger: 'axis'
  },
  legend: {
    data: ['EMG and IMU action', 'Actual action'],
    x: 'center',
    y: 'bottom'
  },
  toolbox: {
    feature: {
      saveAsImage: {}
    }
  },
  grid: {
    show: 'true',
    borderWidth: '2',
    borderColor: '#000000'
  },
  xAxis: {
    name : 'Feature vector number',
    type: 'category',
    splitLine: {
      show: false,
    },
    axisLabel: {
      interval: 1
    },
    data: chart01_X
  },
  yAxis: {
    name : 'Sport mode',
    type: 'value',
    splitLine: {
      show: false,
    },
    max: 6,
    minInterval: 5,
    interval: 5,
  },
  series: [
    {
      name: 'EMG and IMU action',
      type: 'line',
      lineStyle: {
        color: '#a0f0eb',
        width: 2,
        type: 'dashed'
      },
      data: chart01_Y01
    },
    {
      name: 'Actual action',
      type: 'line',
      step: 'start',
      lineStyle: {
        color: '#000000',
        width: 2,
      },
      data: chart01_Y02
    },
  ]
}

export default {
  name: 'HomeView',
  components: {},
  data() {
    return {}
  },
  mounted() {
    this.drawChart();
  },
  methods: {

    drawChart() {
      this.drawChart01();
      this.drawChart02();
      this.drawChart03();
      this.drawChart04();
    },

    drawChart01() {
      let chartDom01 = document.getElementById('charts01');
      let myChart = echarts.init(chartDom01);
      myChart.setOption(option01);
    },
    drawChart02() {
    },
    drawChart03() {
    },
    drawChart04() {
    },
  }
}
</script>


<style>


</style>