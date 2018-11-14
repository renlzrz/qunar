<template>
    <div class="icons" >
        <swiper>
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
        data: function () {
          return {
            iconList:[{
              id: '0001',
              imgUrl:'../../../../static/20181114153610.jpg',
              desc:'景点门票'
              },{
              id: '0002',
              imgUrl:'../../../../static/20181114153648.jpg',
              desc:'滑雪季'
              },{
              id: '0003',
              imgUrl: '../../../../static/20181114153729.jpg',
              desc: '泡温泉'
              },{
              id: '0004',
              imgUrl: '../../../../static/20181114153729.jpg',
              desc: '动物园'
            },{
              id: '0005',
              imgUrl: '../../../../static/20181114153746.jpg',
              desc: '一日游'
            },{
              id: '0006',
              imgUrl: '../../../../static/20181114153746.jpg',
              desc: '必有绑定'
            },{
              id: '0007',
              imgUrl: '../../../../static/20181114153648.jpg',
              desc: '自然风光'
            },{
              id: '0008',
              imgUrl: '../../../../static/20181114153610.jpg',
              desc: '全部'
            },{
              id: '0009',
              imgUrl: '../../../../static/20181114153746.jpg',
              desc: '一日游'
            }
            ]
          }
      },
        computed: {
          pages () {
              const pages = []
              this.iconList.forEach((item,index) => {
                  const page = Math.floor(index/8)
                  if(!pages[page]) {
                    pages[page] = []
                  }
                  pages[page].push(item)
                })
              return pages;
          }
        }
      }
</script>

<style lang="less" scoped>
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
