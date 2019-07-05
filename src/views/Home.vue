<template>
  <div>
    <!-- start 搜索 -->
    <van-search
      v-model="keyword"
      placeholder="请输入搜索关键词"
      show-action
      shape="round"
      @search="onSearch"
    >
      <div slot="action" @click="onSearch">搜索</div>
    </van-search>
    <!-- 搜索 end -->
    <!-- start 轮播 -->
    <van-swipe :autoplay="3000">
      <van-swipe-item v-for="(image, index) in images" :key="index">
        <img :src="image" style="width:10rem;"/>
      </van-swipe-item>
    </van-swipe>
    <!-- 轮播 end -->
    <!-- start 菜单 -->
    <van-grid :border="false">
      <van-grid-item
        v-for="(item,index) in menu"
        :key="index"
        :icon="item.img"
        :text="item.name"
        :to="item.url"
      />
    </van-grid>
    <!-- 菜单 end -->
    <!-- start 公告 -->
      <div class="notice">
        <div class="notice-left">
          <img src="http://local.shopv2.com/addons/ewei_shopv2/static/images/hotdot.jpg" alt="">
        </div>
        <div class="notice-right">
          <van-swipe :autoplay="3000" height="20" :show-indicators="false" vertical>
            <van-swipe-item><div class="text">德味驾控”新选择，试驾新款捷达VS5</div></van-swipe-item>
            <van-swipe-item><div class="text">猫咪蹭你的腿，其实是有原因的！</div></van-swipe-item>
            <van-swipe-item><div class="text">华为P30 Pro新版本发布</div></van-swipe-item>
            <van-swipe-item><div class="text">如果你有小肚子，这四种裙子真的不建议穿</div></van-swipe-item>
          </van-swipe>
        </div>
      </div>
    <!-- 公告 end -->
  </div>
</template>
<script>

export default {
  data() {
    return {
      keyword:"",
      images: [
        'https://img.yzcdn.cn/vant/apple-1.jpg',
        'https://img.yzcdn.cn/vant/apple-2.jpg',
        'https://img.yzcdn.cn/vant/apple-1.jpg',
        'https://img.yzcdn.cn/vant/apple-2.jpg'
      ],
      menu:[
        {
          name:"上衣",
          img:"http://local.shopv2.com/addons/ewei_shopv2/plugin/diypage/static/template/default1/menu_5.png",
          url:"category"
        },{
          name:"下衣",
          img:"http://local.shopv2.com/addons/ewei_shopv2/plugin/diypage/static/template/default1/menu_7.png",
          url:"home"
        },{
          name:"鞋子",
          img:"http://local.shopv2.com/addons/ewei_shopv2/plugin/diypage/static/template/default1/menu_8.png",
          url:"category"
        },{
          name:"内衣",
          img:"http://local.shopv2.com/addons/ewei_shopv2/plugin/diypage/static/template/default1/menu_9.png",
          url:"home"
        },
        {
          name:"商品砍价",
          img:"http://local.shopv2.com/addons/ewei_shopv2/plugin/diypage/static/template/default1/menu_2.png",
          url:"home"
        },{
          name:"拼团抢购",
          img:"http://local.shopv2.com/addons/ewei_shopv2/plugin/diypage/static/template/default1/menu_3.png",
          url:"home"
        },{
          name:"订单",
          img:"http://local.shopv2.com/addons/ewei_shopv2/plugin/diypage/static/template/default1/menu_4.png",
          url:"home"
        },{
          name:"签到",
          img:"http://local.shopv2.com/addons/ewei_shopv2/plugin/diypage/static/template/default1/menu_6.png",
          url:"home"
        },
      ]
    }
  },
  methods: {
    onSearch(){
      console.log(this.keyword);
      this.keyword = ""
    }
  },
}
</script>
<style lang="less">
  .notice{
    display: flex;
    padding: 10px;
    height: 20px;
    line-height: 20px;
    .notice-left{
      padding-right: 20px;
      border-right: 1px solid #ddd;
      img{
        height: 20px;
      }
    }
    .notice-right{
      padding-left: 10px;
      flex:1;
      overflow: hidden;
      .text{
        font-size: 13px;
        color:#666;
      }
    }
  }
</style>