<template>
  <div id="tab-bar">
    <slot></slot>
  </div>
</template>
<script>
export default {
  name: "TabBar"
}
</script>

<style scoped>
/*导入样式*/
@import "../../assets/css/base.css";
#tab-bar{
  display: flex;
  background-color: #f6f6f6;
  height: 49px;
  position: fixed;
  left: 0;
  bottom: 0;
  right: 0;
  box-shadow: 0px -3px 10px rgba(100,100,100,0.5);
  margin: 0;
  padding: 0;
}
</style>