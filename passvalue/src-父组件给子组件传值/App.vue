<template>
  <div id="app">
    <h2>App根基组件</h2>
    <!-- 通过属性值方式给子组件传值 -->
    <!-- 修饰子组件button按钮文字颜色 -->
    <Son se="green"></Son>
    <Son></Son>
    <!-- 属性值来源:直接声明或者data成员,应用data成员则需要进行属性绑定 -->
    <Son :se="cc"></Son>
  </div>
</template>

<script>
import Son from '@/components/son.vue'
export default {
  name: 'App',
  components: {
    Son
  },
  data () {
    return {
      cc: 'purple'
    }
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
