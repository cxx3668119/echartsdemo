<template>
  <div class="home">
    <top-view />
    <sales-view />
    <map-view />
    <bottom-view />
  </div>
</template>

<script>
import TopView from '../components/TopView'
import MapView from '../components/MapView.vue'
import BottomView from '../components/BottomView.vue'
import SalesView from '../components/SalesView.vue'

export default {
  name: 'Home',
  components: {
    TopView,
    MapView,
    SalesView,
    BottomView
  }
}
</script>

<style lang="scss">
.home {
  width: 100%;
  height: 100%;
  padding: 20px;
  box-sizing: border-box;
  background: #eee;
}
</style>