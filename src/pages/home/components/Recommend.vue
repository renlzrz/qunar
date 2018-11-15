<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <li class="item border-bottom" v-for="item of list">
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
      props: {
        list: Array
      }

    }


</script>

<style lang="stylus" scoped>
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
