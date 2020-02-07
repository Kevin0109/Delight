<template>
  <div id="son">
      <!-- 同时进行属性绑定 -->
      <button :style="{color:se}">我是按钮</button>
      <!-- 调用父组件声明的事件,并传递信息,完成修改 -->
      <!-- 使用方法一时的格式 -->
      <!-- <button @click="$emit('gai','red')">修改颜色</button> -->

      <!-- 使用方法二、方法三、终极版方法的格式 -->
      <button @click="$emit('update:se','red')">修改颜色</button>
  </div>
</template>

<script>
export default {
  name: 'Son',
  // 对父组件传递的数据进行接收,props有两种方式
  // props: ['se']
  props: {
    se: {
      type: String, // 设置数据类型,Boolean Number Object Array等
      default: 'blue' // 如果不传值,默认为pink色
    }
  }
}
</script>

<style lang="less" scoped>
#son {
  width: 390px;
  height: 100px;
  border:2px solid #ff3040;
  margin:5px 2px;
}
</style>
