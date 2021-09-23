<template>
    <tab-bar>
      <tab-bar-item path="/home" activeColor="red">
        <span slot="item-icon" class="iconfont icon">&#xe61d;</span>
        <!--        <span slot="item-icon-active" class="iconfont-active iconfont icon">&#xe61d;</span>-->
        <div slot="item-text">首页</div>
      </tab-bar-item>
      <tab-bar-item path="/category" activeColor="red">
        <span slot="item-icon" class="iconfont icon">&#xe7f9;</span>
        <!--        <span slot="item-icon-active" class="iconfont-active iconfont icon">&#xe7f9;</span>-->
        <div slot="item-text">分类</div>
      </tab-bar-item>
      <tab-bar-item path="/cart" activeColor="red">
        <span slot="item-icon" class="iconfont icon">&#xe670;</span>
        <!--        <span slot="item-icon-active" class="iconfont-active iconfont icon">&#xe670;</span>-->
        <div slot="item-text">购物车</div>
      </tab-bar-item>
      <tab-bar-item path="/profile" activeColor="red">
        <span slot="item-icon" class="iconfont icon">&#xe61b;</span>
        <!--        <span slot="item-icon-active" class="iconfont-active iconfont icon">&#xe61b;</span>-->
        <div slot="item-text">我的</div>
      </tab-bar-item>
    </tab-bar>
</template>

<script>
import TabBar from '../../common/tabber/TabBar'
import TabBarItem from "../../common/tabber/TabBarItem"

export default {
  name: "MainTabBar",
  components: {
    TabBar,
    TabBarItem
  }
}
</script>

<style scoped>

</style>
