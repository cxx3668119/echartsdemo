<template>
  <common-card title="累计用户数" value='1,160,802'>
    <template>
      <div class="total-user-charts" :style="{width:'100%',height:'100%'}"></div>
    </template>

    <template v-slot:footer>
      <div class="total-total-footer">
        <span>日同比 </span>
        <span class="size1"> 65.98%</span>
        <div class="increase">
        </div>
        <span>月同比 </span>
        <span class="size1"> 107.48%</span>
        <div class="decrease">
        </div>
      </div>
    </template>
  </common-card>
</template>

<script>
import CommonCard from "../components/CommonCard"
export default {
  name: "TotalUser",
  components: {
    CommonCard,
  },
  mounted() {
    const chartDom = document.querySelector('.total-user-charts');
    const chart = this.$echarts.init(chartDom);
    chart.setOption({
      xAxis: {
        type: 'value',
        // type: 'category',
        show: false
      },
      yAxis: {
        type: 'category',
        // type: 'value',
        show: false
      },
      series: [{
        type: 'bar',
        stack: '总量',
        barWidth: 10,
        data: [200],
        itemStyle: {
          color: '#45c946'
        }
      }, {
        type: 'bar',
        stack: '总量',
        data: [250],
        itemStyle: {
          color: '#eeeeee'
        }
      }, {
        type: 'custom',
        data: [200],
        stack: '总量',
        renderItem: (params, api) => {
          const value = api.value(0)
          const endPoint = api.coord([value, 0])
          return {
            type: 'path',
            position: endPoint,
            shape: {
              d: '',
              x: 0,
              y: 0,
              width: 20,
              height: 20,
            }
          }
        }
      }
      ],
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

<style lang="scss">
.total-total-footer {
  display: flex;
  align-items: center;
  .increase {
    width: 0;
    height: 0;
    border-width: 4px;
    border-color: transparent transparent red transparent;
    border-style: solid;
    margin: 0% 9px 3px 5px;
  }
  .decrease {
    width: 0;
    height: 0;
    border-width: 4px;
    border-color: green transparent transparent transparent;
    border-style: solid;
    margin: 3px 0 0px 5px;
  }
}
</style>