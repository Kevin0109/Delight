<template>
  <div id="app">
    <h2>App根基组件</h2>
    <first></first>
    <second></second>
  </div>
</template>

<script>
// 对兄弟组件进行导入、注册、使用
import first from '@/components/first.vue'
import second from '@/components/second.vue'
export default {
  name: 'App',
  components: {
    first,
    second
  }
}
</script>

<style lang="less" scoped>
#app {
  width: 400px;
  height: 600px;
  border:3px solid orange;
}
</style>
