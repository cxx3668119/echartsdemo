<template>
  <common-card title="累计订单量" value='2,353,711'>
    <template>
      <div class="total-id-char" :style="{width:'100%',height:'100%'}"></div>
    </template>
    <template v-slot:footer>
      <div>
        <span>昨日订单量 </span>
        <span class="money">¥ 2,000,000</span>
      </div>
    </template>
  </common-card>
</template>

<script>
import CommonCard from "../components/CommonCard"
export default {
  name: "TotalOrder",
  components: {
    CommonCard,
  },
  mounted() {
    const chartDom = document.querySelector('.total-id-char');
    const chart = this.$echarts.init(chartDom);
    chart.setOption({
      xAxis: {
        type: 'category',
        show: false,
        boundaryGap: false//坐标轴两边留白策略
      },
      yAxis: {
        show: false
      },
      series: [{
        type: 'line',
        data: [620, 432, 220, 534, 790, 430, 220, 320, 532, 320, 834, 690, 530, 220, 620],
        areaStyle: {
          color: 'purple'
        },
        lineStyle: {//图形上方的线
          width: 0
        },
        itemStyle: {//图形上方的点
          opacity: 0
        },
        smooth: true //弧度
      }],
      grid: {//位置
        top: 0,
        left: 0,
        right: 0,
        bottom: 0
      }
    })
  },
}
</script>

<style>
</style>