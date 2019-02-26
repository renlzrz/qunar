<template>
    <div class="icons" >
        <swiper :options="swiperOption">
          <!-- slides -->
          <swiper-slide v-for="(page,index) of pages" :key="index">
            <div class="icon" v-for="item of page" :key="item.id">
              <div class="icon-img">
                <img class="icon-img-content" :src='item.imgUrl' alt="">
              </div>
              <p class="icon-desc">{{item.desc}}</p>
            </div>
          </swiper-slide>

          <!-- Optional controls -->
          <div class="swiper-pagination"  slot="pagination" style=""></div>
        </swiper>
      </div>
</template>

<script>
    export default {
      name: "HomeIcons",
      props: {
        list: Array
      },
      data: function() {
        return {
          swiperOption: {
            autoplay:false
          }
        }
      },
      computed: {
        // 每页图标个数设置
        pages () {
            const pages = []
            this.list.forEach((item,index) => {
                const page = Math.floor(index/8)
                if(!pages[page]) {
                  pages[page] = []
                }
                pages[page].push(item)
              })
            return pages
        }
      }
    }
</script>

<style lang="stylus" scoped>
  .icons /deep/ .swiper-container {
    height: 0;
    padding-bottom: 50%;
  }
    .icon {
      position: relative;
      overflow: hidden;
      float: left;
      height: 0;
      width: 25%;
      padding-bottom: 25%;
      .icon-desc{
        position: absolute;
        top: 72%;
        left: 0;
        right: 0;
        height:.44rem;
        line-height: 0.44rem;
        color: #333;
        text-align: center;
      }
      .icon-img {
        position: absolute;
        top: 0;
        left: 0;
        right: 0;
        bottom:.44rem;
        box-sizing: border-box;
        padding:0.1rem ;
        .icon-img-content {
          height: 100%;
          display: block;
          margin: 0 auto;
        }
      }
    }


</style>
