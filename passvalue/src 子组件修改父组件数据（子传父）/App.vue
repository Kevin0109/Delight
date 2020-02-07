<template>
  <div id="app">
    <h2>App根基组件</h2>
    <!-- 通过属性值方式给子组件传值 -->
    <!-- 修饰子组件button按钮文字颜色 -->
    <!-- 属性值来源:直接声明或者data成员,应用data成员则需要进行属性绑定 -->
    <!-- <Son :se="cc"></Son> -->
    <!-- 给子组件添加一个事件,完成对cc的修改 -->
    <!-- 事件驱动不要添加(),否则会显示undefined -->
    <!-- <Son :se="cc" @gai="amend"></Son> -->

    <!-- 方法二:使用箭头函数,就不用设置methods方法了 -->
    <!-- <Son :se="cc" @gai="data=>{cc=data}"></Son> -->

    <!-- 方法三: 通过update格式,给自足家添加事件 -->
    <!-- <Son :se="cc" @update:se="data=>{cc=data}"></Son> -->

    <!-- 终极版方法: sync修饰符方法 :se.sync='cc' 相当于是对:se="cc" @update:se="data=>{cc=data}"的封装 -->
    <Son :se.sync="cc"></Son>
  </div>
</template>

<script>
// 对son子组件进行导入、注册、使用
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
  },
  methods: {
    // 完成cc的修改
    // data是事件的形参,由子组件中传递过来的red
    amend (data) {
      this.cc = data
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
