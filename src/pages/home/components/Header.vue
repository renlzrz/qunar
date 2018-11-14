<template>
  <div class="header">
    <div class="header-left"><span class="iconfont">&#xe624;</span></div>
    <div class="header-input"><span class="iconfont">&#xe632;</span>输入城市景点</div>
    <div class="header-right">城市<span class="arrow-icon iconfont ">&#xe64a;</span></div>
  </div>
</template>

<script>
    export default {
        name: "HomeHeader"
    }
</script>

<style lang="less" scoped>


  .header {
    height: 0.86rem;
    line-height: 0.86rem;
    display: flex;
    background: #00bcd4;
    color: #fff;
    .header-left {
      width: 0.64rem;
      float: left;
      .iconfont {
        margin-left: 0.13rem;
      }
    }
    .header-right {
      width: 1.1rem;
      float: right;
      .arrow-icon {
        font-size: 0.3rem;
        margin-left: 0.1rem;
      }
    }
    .header-input {
      flex: 1;
      line-height: 0.64rem;
      height: 0.64rem;
      margin-top: 0.12rem;
      margin-right: 0.2rem;
      background: #fff;
      border-radius: 0.1rem ;
      color: #ccc;
    }

  }

</style>
