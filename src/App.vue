<template>
  <div id="app">
    <div class="baidumap" id="allmap"></div>
    <img alt="Vue logo" src="./assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
  },
  mounted() {
    this.baiduMap();
  },
  methods: {
    baiduMap() {
      var map = new window.BMap.Map("allmap"); //创建地图

      map.enableScrollWheelZoom();
      // 启用滚轮放大缩小;
      var point = new window.BMap.Point(114.12883, 22.688615); //设置地图位置
      map.centerAndZoom(point, 12);
      var marker = new window.BMap.Marker(point); // 创建标注
      map.addOverlay(marker); // 将标注添加到地图中
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.baidumap {
  width: 500px;
  height: 200px;
  border: 1px solid red;
}
</style>
