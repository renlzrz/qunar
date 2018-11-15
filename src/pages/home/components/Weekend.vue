<template>
  <div>
    <div class="title">周末去哪</div>
    <ul>
      <li class="item border-bottom" v-for="item of list">
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
    props: {
      list:Array
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
  .item-img-wrapper {
    height: 0;
    overflow: hidden;
    padding-bottom: 37.1%;
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
