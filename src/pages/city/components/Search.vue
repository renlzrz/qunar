<template>
  <div>
    <div class="search">
      <input class="search-input" type="text"
             v-model="keyword" placeholder="输入城市名">
    </div>
    <div class="search-content" ref="search" v-show="keyword">
      <ul>
        <li class="search-item border-bottom" v-for="item of list"
            :key="item.id" @click="handleCityClick(item.name)">
          {{item.name}}
        </li>
        <li class="search-item border-bottom"
            v-show="!list.length">
          没有符合的城市</li>
      </ul>
    </div>
  </div>

</template>

<script>
    import Bscroll from 'better-scroll'
    export default {
      name: "CitySearch",
      props: {
        cities:''
      },
      data: function () {
        return {
          keyword:'',
          list:[],
          timer: null
        }
      },
      // 输入城市名找到符合城市
      watch: {
        keyword () {
          if(this.timer) {
            clearTimeout(this.timer)
          }
          // 没有输入则为空
          if (!this.keyword) {
            this.list = []
            return
          }
          // 设置间隔减少性能消耗
          this.timer = setTimeout(() => {
            const result = []
            for (let i in this.cities) {
              this.cities[i].forEach((value) => {
                if (value.spell.indexOf(this.keyword) > -1 ||
                value.name.indexOf(this.keyword) > -1) {
                result.push(value)}
              })
            }
            this.list = result
          },100)
        }
      },
      methods: {
        handleCityClick(city) {
          this.$store.commit('changeCity',city)
          this.$router.push('/')
        }
      },
      mounted: function () {
        // 滑动组件
        this.scroll = new Bscroll(this.$refs.search)
      }
    }
</script>

<style lang="stylus" scoped>
  @import "../../../assets/styles/varibles.styl"
  .search {
    height: 0.72rem
    padding: 0.1rem
    background: $bgColor
    .search-input {
      width: 100%
      height:0.62rem
      line-height: 0.62rem
      text-align: center
      border-radius:0.06rem
    }
  }
  .search-content {
    z-index: 1
    overflow: hidden
    position: absolute
    top: 1.68rem
    left: 0
    right: 0
    bottom: 0
    background: #eee
    .search-item {
      line-height:0.62rem
      padding-left:0.2rem
      background: #fff
      color: #666
    }
  }



</style>
