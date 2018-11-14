<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <li class="item border-bottom" v-for="item of recommendList">
        <img class="item-img" :src="item.imgUrl">
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
        </div>

      </li>
    </ul>
  </div>

</template>

<script>
    export default {
      name: "HomeRecommend",
      data: function() {
        return {
          recommendList: [{
            id:'0001',
            imgUrl: '../../../../static/20181114174615.jpg',
            title:'大连圣亚海洋世界',
            desc:'浪漫大连首站，浪漫的海洋世界'
          },{
            id:'0002',
            imgUrl: '../../../../static/20181114174615.jpg',
            title:'大连圣亚海洋世界',
            desc:'浪漫大连首站，浪漫的海洋世界'
          },{
            id:'0003',
            imgUrl: '../../../../static/20181114174615.jpg',
            title:'大连圣亚海洋世界',
            desc:'浪漫大连首站，浪漫的海洋世界'
          }]
        }

      }

    }
</script>

<style lang="less" scoped>
  .title {
    margin-top: 0rem;
    line-height: 0.8rem;
    background: #eee;
    text-indent: 0.2rem;
  }
  .item {
    display: flex;
    height: 1.9rem;
    overflow: hidden;

    .item-img {
      width: 1.7rem;
      height: 1.7rem;
      padding: 0.1rem;
    }
    .item-info {
      flex: 1;
      padding: 0.1rem;
      .item-title {
        line-height: 0.54rem;
        font-size: 0.32rem;
      }
      .item-desc {
        line-height: 0.4rem;
        color: #ccc;
      }
      .item-button {
        line-height: 0.44rem;
        margin-top: 0.16rem;
        background: #ff9300;
        padding: 0 0.1rem;
        border-radius: 0.6rem;
        color: #fff;
      }
    }

  }
</style>
