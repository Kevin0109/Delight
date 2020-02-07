<template>
  <div id="second">
      <h3>我是小弟(数据发送方)</h3>
      <button @click="back()">给大哥回话</button>
  </div>
</template>

<script>
// 导入bus对象
import bus from '@/bus.js'

export default {
  name: 'second',
  methods: {
    back () {
    // bus调用自己的事件
      bus.$emit('receive', '1000元保护费')
    }
  }
}
</script>

<style lang="less" scoped>
#second {
    width: 380px;
    height: 120px;
    border: 2px solid blue;
    margin:10px;
}
</style>
