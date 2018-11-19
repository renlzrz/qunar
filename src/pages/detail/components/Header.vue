<template>
  <div>
    <router-link tag="div" to="/" class="header-abs" v-show="showAbs" >
      <div class="iconfont head-abs-back">&#xe624;</div>
    </router-link>
    <div class="header-fixed" v-show="!showAbs" :style="opacityStyle">
      <router-link  to="/" >
        <div class="iconfont header-fixed-back">&#xe624;</div>
      </router-link>
      景点详情
    </div>
  </div>
</template>

<script>
  export default {
    name: "DetailHeader",
    data:function () {
      return {
        showAbs:true,
        opacityStyle: {
          opacity: 0
        }
      }
    },
    methods: {
      handleScroll () {
        const top = document.documentElement.scrollTop  //屏幕滚动距离
        if (top > 60) {
          let opacity = top/140
          opacity = opacity > 1?1:opacity
          this.opacityStyle = { opacity }
          this.showAbs = false
        } else {
          this.showAbs = true
        }

      }
    },
    activated: function () {
      window.addEventListener('scroll', this.handleScroll)
    }
  }
</script>

<style lang="stylus" scoped>
  @import "../../../assets/styles/varibles.styl"
  .header-abs {
    position: absolute
    left: 0.2rem
    top: 0.2rem
    width:0.8rem
    height:0.8rem
    line-height: 0.8rem
    border-radius: 0.4rem
    text-align: center
    background: rgba(0,0,0,0.8)
    .head-abs-back {
      color: #fff
      font-style: 0.4rem
    }
  }
  .header-fixed {
    position: fixed
    top: 0
    left: 0
    right: 0

    height: $headerHeight
    line-height: $headerHeight
    text-align: center
    color: #fff
    background: #00bcd4
    font-size: 0.32rem
    .header-fixed-back {
      position: absolute
      width: .64rem
      text-align: center
      font-size: .4rem
      color: #fff
    }
  }

</style>
