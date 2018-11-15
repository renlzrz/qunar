<template>

  <div class="wrapper">
    <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide v-for="item in list" :key="item.id">
        <img :src="item.imgUrl" class="swiper-img">
      </swiper-slide>

      <!-- Optional controls -->
      <div class="swiper-pagination"  slot="pagination" style=""></div>
    </swiper>

  </div>

</template>

<script>
    export default {
      name: "HomeSwiper",
      props: {
        list:Array
      },
      data: function () {
        return {
          swiperOption: {
            pagination: '.swiper-pagination',
            loop:true
          }
        }

      }
    }

</script>

<!--样式穿透-->
<!--<style>-->
  <!--.swiper-pagination-bullet-active {-->
    <!--background-color: #fff !important;-->
  <!--}-->
<!--</style>-->

<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active {
    background-color: #fff !important;
  }
  .wrapper {
    overflow: hidden;
    width: 100%;
    height: 0;
    padding-bottom: 31.0%;
    .swiper-img {
      width: 100%;
    }
  }

</style>

