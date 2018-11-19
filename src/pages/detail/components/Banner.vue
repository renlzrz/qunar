<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img class="banner-img" src="../../../../static/20181118111523.jpg" alt="">
      <div class="banner-info">
        <div class="banner-tittle">大连圣亚海洋世界</div>
        <div class="banner-number"><span class="iconfont banner-fcon">&#xe692;</span>39</div>
      </div>
    </div>
    <common-gallary :imgs="imgs" v-show="showGallary"
    @close="handleGallaryClose">

    </common-gallary>
  </div>

</template>

<script>
  import CommonGallary from 'common/gallary/Gallary'
  export default {
    name: "DetailBanner",
    data: function () {
      return {
        showGallary:false,
        imgs:['../../../static/20181118111523.jpg']
      }

    },
    methods: {
      handleBannerClick () {
        this.showGallary = true
      },
      handleGallaryClose () {
        this.showGallary = false
      }
    },
    components: {
      CommonGallary
    }
  }
</script>

<style lang="stylus" scoped>
  .banner {
    position: relative
    overflow: hidden
    height: 0
    padding-bottom:55%
    .banner-img {
      width:100%
    }
    .banner-info {
      display: flex
      position: absolute
      left:0
      right:0
      bottom:0.44rem
      line-height:0.6rem
      color: #fff
      background-image:linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,0.8))
      .banner-tittle {
        flex:1
        font-style: 0.32rem
        padding:0.2rem
      }
      .banner-number {
        margin-top: 0.22rem
        padding:0.2rem
        line-height:0.12rem
        height:0.12rem
        border-radius 0.2rem
        background: rgba(0,0,0,0.8)
        font-style: 0.24rem
        .banner-icon {
          font-style: 0.24rem
        }
      }
    }
  }

</style>
