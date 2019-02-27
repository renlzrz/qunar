<template>
  <div id="app">

    <keep-alive exclude="Detail"> <!--缓存作用-->
      <router-view></router-view>
    </keep-alive>

  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>


<style>
</style>
