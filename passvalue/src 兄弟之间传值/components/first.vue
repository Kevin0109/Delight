<template>
  <div id="first">
      <h3>我是大哥(数据接收方)</h3>
      <p>{{msg}}</p>
  </div>
</template>

<script>
// 导入bus对象
import bus from '@/bus.js'

export default {
  name: 'first',
  data () {
    return {
      // 接收小弟传递的信息
      msg: ''
    }
  },
  // 要在最初就给bus声明事件
  created () {
    // 给bus声明事件要使用$on
    bus.$on('receive', (data) => {
      this.msg = '我已收到' + data
    })
  }

}
</script>

<style lang="less" scoped>
#first {
    width: 380px;
    height: 200px;
    border: 2px solid green;
    margin:10px;
}
</style>
