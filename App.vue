<template>
  <div class="app">
    <van-nav-bar title="长沙前端-1903" left-text="返回" left-arrow @click-left="onClickLeft" />
    <transition name="fly">
      <router-view></router-view>
    </transition>
    <van-tabbar v-model="active">
      <van-tabbar-item icon="home-o" to="/home">home</van-tabbar-item>
      <van-tabbar-item icon="friends-o" to="/friends">friends</van-tabbar-item>
      <van-tabbar-item icon="shopping-cart-o" to="/cart" info="5">cart</van-tabbar-item>
      <van-tabbar-item icon="search" to="/search">search</van-tabbar-item>
    </van-tabbar>
  </div>
</template>
<script>
export default {
  data: () => ({
    active: 0
  }),
  created() {},
  methods: {
    onClickLeft() {
      console.log('left')
    }
  }
}
</script>
<style lang="less" scoped>
.app {
  // 一屏幕 容不下 三屏
   overflow-x: hidden;
  .fly-enter {
    transform: translateX(100%);
  }
  .fly-leave-to {
    transform: translateX(-100%);
    position: absolute;
    // left: -300%
  }

  .fly-enter-active,
  .fly-leave-active {
    transition: all .3s ease;
  }
}
</style>
