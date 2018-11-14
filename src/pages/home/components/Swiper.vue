<template>

  <div class="wrapper">
    <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide v-for="item in swiperList" :key="item.id">
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
        data: function () {
          return {
            swiperOption: {
              pagination: '.swiper-pagination',
              loop:true
            },
            swiperList: [{
              id:'0001',
              imgUrl:'//img1.qunarzz.com/vc/a5/e0/64/c6bd8680fb67247db15df6057b.jpg'
            },{
              id:'0002',
              imgUrl:'//img1.qunarzz.com/vc/2f/8e/51/cb4d31b360c836f7d1bbe83c13.jpg'
            },{
              id:'0003',
              imgUrl:'//img1.qunarzz.com/vc/a4/29/dd/4a0734b77f675da2a8ca4a9879.jpg'
            }]
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

<style lang="less" scoped>
  .wrapper /deep/ .swiper-pagination-bullet-active {
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

