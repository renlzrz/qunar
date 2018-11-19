<template>
  <ul class="list">
    <li class="item" v-for="item in letters" :key="item" :ref="item"
        @click="handleLetterClick" @touchstart="handleTouchStart"
        @touchmove="handleTouchMove" @touchend="handleTouchEnd"
    >{{item}}
    </li>

  </ul>
</template>

<script>
  export default {
    name: "CityAlphabet",
    props: {
      cities:Object
    },
    // 显示右侧字幕列表
    computed: {
      letters () {
        const letters = []
        for (let i in this.cities) {
          letters.push(i)
        }
        return letters
      }
    },
    data: function () {
      return {
        touchStatus: false,
        startY:0
      }
    },
    updated: function () {
      this.startY = this.$refs['A'][0].offsetTop
    },
    // 滑动右侧字母匹配城市列表
    methods: {
      handleLetterClick (e) {
        this.$emit('change', e.target.innerText)
      },
      handleTouchStart () {
        this.touchStatus = true
      },
      handleTouchMove (e) {
        if (this.touchStatus) {
          const touchY = e.touches[0].clientY - 79
          const index = Math.floor((touchY - this.startY)/20)
          if (index >= 0 && index < this.letters.length) {
            this.$emit('change',this.letters[index])
          }

        }
      },
      handleTouchEnd () {
        this.touchStatus = false
      }
    }
  }
</script>

<style lang="stylus" scoped>
  .list {
    display: flex;
    flex-direction: column;
    justify-content: center;
    position: absolute;
    top:1.58rem;
    right: 0;
    bottom: 0;
    width: 0.4rem;
    .item {
      line-height:0.4rem;
      text-align: center;
      color: #00bcd4;
    }
  }

</style>
