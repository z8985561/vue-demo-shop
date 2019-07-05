<template>
  <div>
    <van-tabbar @change="handleChangeActive" :safe-area-inset-bottom="true" v-model="active">
      <van-tabbar-item name="home" icon="home-o" to="/home">首页</van-tabbar-item>
      <van-tabbar-item name="category" icon="apps-o" to="/category">分类</van-tabbar-item>
      <van-tabbar-item name="cart" icon="shopping-cart-o" to="/cart">购物车</van-tabbar-item>
      <van-tabbar-item name="user" icon="user-o" to="/user">个人中心</van-tabbar-item>
    </van-tabbar>
  </div>
</template>
<script>
export default {
    data() {
      return {
        active: 'home'
      }
    },
    methods: {
      handleChangeActive(e){
        console.log(e);
        this.active = e;
      }
    },
}
</script>
