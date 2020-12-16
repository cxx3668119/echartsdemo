<template>
  <common-card title="今日交易用户数" value='180,997'>
    <template>
      <div class="today-user-char" :style="{width:'100%',height:'100%'}"></div>
    </template>
    <template v-slot:footer>
      <div>
        <span>退货率 </span>
        <span class="money">5.38%</span>
      </div>
    </template>
  </common-card>
</template>

<script>
import CommonCard from "../components/CommonCard"
export default {
  name: "TodayUser",
  components: {
    CommonCard,
  },
  mounted() {
    const chartDom = document.querySelector('.today-user-char');
    const chart = this.$echarts.init(chartDom);
    chart.setOption({
      color: ['#3398DB'],
      xAxis: {
        type: "category",
        data: ['00:00', '01:00', '02:00', '03:00', '04:00', '05:00', '06:00', '07:00', '08:00', "09:00", '10:00', "11:00", "12:00", "13:00"],
        show: false
      },
      yAxis: {
        show: false
      },
      series: [{
        type: 'bar',
        data: [410, 82, 200, 334, 390, 330, 220, 150, 82, 200, 134, 290, 330, 150],
        barWidth: '60%',
      }],
      grid: {
        top: 0,
        right: 0,
        bottom: 0,
        left: 0
      }
    })
  },
}
</script>

<style>
</style>