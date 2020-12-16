<template>
  <common-card title="累计销售额" value='¥ 36,281,538'>
    <template>
      <div class="chart">
        <div class="compare">
          <span>日同比 </span>
          <span class="size1"> 20.94%</span>
          <div class="increase"></div>
        </div>
        <div class="compare">
          <span>月同比 </span>
          <span class="size1"> 56.39%</span>
          <div class="decrease"></div>
        </div>
      </div>

    </template>
    <template v-slot:footer>
      <div>
        <span>昨日销售额 </span>
        <span class="money">¥ 30,000,000</span>
      </div>
    </template>
  </common-card>
</template>

<script>
import CommonCard from "../components/CommonCard"
export default {
  name: "TotalSales",
  components: {
    CommonCard,
  }
}
</script>

<style lang="scss" >
@import url("../assets/css/base.scss");
.chart {
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.compare {
  display: flex;
  font-size: 12px;
  color: #666;
  align-items: center;
  margin-top: 3px;
  .increase {
    width: 0;
    height: 0;
    border-width: 4px;
    border-color: transparent transparent red transparent;
    border-style: solid;
    margin: 0% 0 3px 5px;
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
.money {
  margin-left: 5px;
  color: #333;
  font-weight: 700;
}
</style>