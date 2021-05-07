<template>
  <div class="tab-bar-item" @click="btnClick">
    <div v-if="!isActive">
      <slot name="item-icon"></slot>
    </div>
    <div v-else>
      <slot name="item-icon-active"></slot>
    </div>
    <div :style="activeStyle">
      <slot name="item-text"></slot>
    </div>
    <!--    <img src="../assets/img/tabbar/home.png" alt="首页">-->
    <!--    <div>首页</div>-->
  </div>
</template>

<script>
export default {
  name: "TabItem",
  props: {
    path: String,
    activeColor: {
      type: String,
      default: 'red'
    }
  },
  computed: {
    isActive() {
      return this.$route.path.includes(this.path)
    },
    activeStyle() {
      // console.log(this.isActive);
      return this.isActive ? {color:this.activeColor} : {}
    }
  },
  methods: {
    btnClick() {
      this.$router.replace(this.path);
    }
  }
}
</script>

<style scoped>
.tab-bar-item {
  flex: 1;
  list-style: none;
  height: 49px;
  text-align: center;
  font-size: 15px;
}

.tab-bar-item img {
  width: 24px;
  height: 24px;
  margin-top: 3px;
  vertical-align: middle;
  margin-bottom: 3px;
}

/*.active{*/
/*  color: rgb(228, 61, 64);*/
/*}*/
</style>