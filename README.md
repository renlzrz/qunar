# vue-qunar

> A Vue.js project

## 首页header开发
>iconfont的使用

>首页轮播图

使用插件 VueAwesomeSwiper

>样式穿透

.swiper-pagination-bullet-active {
    background-color: #fff !important;
  }


或者

.wrapper /deep/ .swiper-pagination-bullet-active {
    background-color: #fff !important;
  }
  
swiperOption: {
                pagination: '.swiper-pagination',
                loop:true //循环播放
               }

>首页图标区域

>推荐组件

>周末游组件

>ajax获取首页数据

>父子组件数据传递


## 城市列表页面开发

>城市选择路由配置

<router-link to="/city"></router-link>

>better-scroll的使用

>页面动态数据渲染
