<template>
  <div>
    <div class="title">周末去哪</div>
    <ul>
      <li class="item border-bottom" v-for="item of recommendList">
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl">
        </div>

        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>

      </li>
    </ul>
  </div>

</template>

<script>
  export default {
    name: "HomeWeekend",
    data: function() {
      return {
        recommendList: [{
          id:'0001',
          imgUrl: '../../../../static/20181114183856.jpg',
          title:'大连圣亚海洋世界',
          desc:'浪漫大连首站，浪漫的海洋世界'
        },{
          id:'0002',
          imgUrl: '../../../../static/20181114183936.jpg',
          title:'大连圣亚海洋世界',
          desc:'浪漫大连首站，浪漫的海洋世界'
        },{
          id:'0003',
          imgUrl: '../../../../static/20181114183856.jpg',
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
  .item-img-wrapper {
    height: 0;
    overflow: hidden;
    padding-bottom: 33.9%;
      .item-img {
        width: 100%;
      }
  }
  .item-info {
    padding: 0.1rem;
    .item-title {
      line-height: 0.54rem;
      font-size: 0.32rem;
    }
    .item-desc {
      line-height: 0.4rem;
      color: #ccc;
    }

  }


</style>
