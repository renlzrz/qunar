<template>
  <div class="search">
    <input class="search-input" type="text" placeholder="输入城市名">
  </div>
</template>

<script>
    export default {
        name: "CitySearch"
    }
</script>

<style lang="stylus" scoped>
  @import "../../../assets/styles/varibles.styl"
  .search {
    height: 0.72rem;
    padding: 0.1rem;
    background: $bgColor;
    .search-input {
      width: 100%;
      height:0.62rem;
      line-height: 0.62rem;
      text-align: center;
      border-radius:0.06rem;
    }
  }


</style>
