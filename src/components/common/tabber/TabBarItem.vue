<template>
  <div class="tab-bar-item" @click="itemClick">
<!--    如果是要替换图片的话，就是搞两个插槽-->
<!--    <div v-if="!isActive"><slot name="item-icon"></slot></div>>-->
<!--    <div v-else><slot name="item-icon-active"></slot></div>-->
<!--    <div :class="{active: isActive}"><slot  name="item-icon"></slot></div>-->
<!--    <div :class="{active: isActive}"><slot  name="item-text"></slot></div>-->
    <div :style="activeStyle"><slot  name="item-icon"></slot></div>
    <div :style="activeStyle"><slot  name="item-text"></slot></div>
  </div>
</template>

<script>
export default {
  name: "TabBarItem",
  props: {
    path: String,
    activeColor: {
      type: String,
      default: 'pink'
    }
  },
  data() {
    return {
      // isActive: false,
      // path: '/home'
    }
  },
  computed: {
    isActive() {
      // /home -> item1(/home) = true
      // /home -> item1(/category) = false
      // /home -> item1(/cart) = false
      // /home -> item1(/profile) = false
      return this.$route.path.indexOf(this.path) !== -1
    },
    activeStyle() {
      return this.isActive ? {color: this.activeColor} : {}
    }

  },
  methods: {
    itemClick() {
      // console.log('itemClick');
      this.$router.replace(this.path)
    }
  }
}
</script>

<style scoped>
.tab-bar-item {
  flex: 1;
  text-align: center;
  height: 49px;
  font-size: 16px;
}

@font-face {
  font-family: "iconfont"; /* Project id 2804226 */
  src: url('../../../assets/img/font/iconfont.woff2?t=1631259302157') format('woff2'),
  url('../../../assets/img/font/iconfont.woff?t=1631259302157') format('woff'),
  url('../../../assets/img/font/iconfont.ttf?t=1631259302157') format('truetype');
}

.iconfont {
  font-family: "iconfont" !important;
  font-size: 22px;
  font-style: normal;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.icon {
  height: 24px;
  margin-top: 3px;
  /*vertical-align: middle;*/
  margin-bottom: 2px
}

.active {
  color: red
}
</style>
