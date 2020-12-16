<template>
  <div class="top-view">
    <el-row :gutter="20">
      <el-col :span="6">
        <el-card shadow="hover">
          <total-sales />
        </el-card>
      </el-col>
      <el-col :span="6">
        <el-card shadow="hover">
          <total-order />
        </el-card>
      </el-col>
      <el-col :span="6">
        <el-card shadow="hover">
          <today-user />
        </el-card>
      </el-col>
      <el-col :span="6">
        <el-card shadow="hover">
          <total-user />
        </el-card>
      </el-col>
    </el-row>

  </div>
</template>

<script>
import TotalSales from "../components/TotalSales"
import TodayUser from './TodayUser.vue'
import TotalOrder from './TotalOrder.vue'
import TotalUser from './TotalUser.vue'
export default {
  name: 'TopView',
  components: {
    TotalSales,
    TotalOrder,
    TodayUser,
    TotalUser,
  }
}
</script>

<style>
</style>