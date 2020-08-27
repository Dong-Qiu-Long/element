<template>
  <div id="app">
    <el-row></el-row>
    <el-col></el-col>
    我是董秋龙
  </div>
</template>

<script>
import ElRow from './components/element/Row.vue';
import ElCol from './components/element/Col.vue';

export default {
  name: 'App',
  components: {
    ElRow,
    ElCol,
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
