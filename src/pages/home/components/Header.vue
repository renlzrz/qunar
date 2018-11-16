<template>
  <div class="header">
    <div class="header-left"><span class="iconfont">&#xe624;</span></div>
    <div class="header-input"><span class="iconfont">&#xe632;</span>输入城市景点</div>
    <router-link to="/city">
      <div class="header-right">
        {{this.$store.state.city}}<span class="arrow-icon iconfont ">&#xe64a;</span>
      </div>
    </router-link>

  </div>
</template>

<script>
    export default {
      name: "HomeHeader",
    }
</script>

<style lang="stylus" scoped>
  @import "../../../assets/styles/varibles.styl"
  .header {
    height: $headerHeight
    line-height: $headerHeight
    display: flex;
    background: #00bcd4;
    color: #fff;
    .header-left {
      width: 0.64rem;
      float: left;
      .iconfont {
        margin-left: 0.13rem;
        font-size:0.39rem;
      }
    }
    .header-right {
      width: 1.1rem;
      float: right;
      color: #fff;
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
