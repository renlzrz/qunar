<template>
  <div class="container" @click="handleGallaryClick">
    <div class="wrapper">
      <swiper>
        <!-- slides -->
        <swiper-slide :options="swiperOption" v-for="(item,index) in imgs"
        :key="index">
          <img :src="item" class="gallary-img">
        </swiper-slide>

        <div class="swiper-pagination"  slot="pagination" style=""></div>
      </swiper>

    </div>
  </div>
</template>

<script>

  export default {
    name: "CommonGallary",
    props: {
      imgs: {
        default () {
          return ['../../../static/20181118111523.jpg']
        }
      }
    },
    data:function () {
      return {
        swiperOption : {
          pagination: '.swiper-pagination',
          paginationType: 'fraction',
          observeParents: true,
          observe: true
        }
      }
    },
    methods: {
      handleGallaryClick () {
        this.$emit('close')
      }
    }
  }
</script>

<style lang="stylus" scoped>
  .container >>> .swiper-container {
    overflow: inherit
  }
  .container {
    display: flex
    flex-direction: column
    justify-content: center
    z-index: 99
    position: fixed
    left: 0
    right:0
    top:0
    bottom:-4rem
    background: #000
    .wrapper {
      overflow: hidden
      height: 0
      width: 100%
      padding-bottom: 100%
      .gallary-img {
        width:100%
      }
      .swiper-pagination {
        color: #fff
        bottom: -1rem
      }
    }
  }

</style>
