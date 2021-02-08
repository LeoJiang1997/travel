<template>
<div class="wrapper">
  <swiper ref="mySwiper" :options="swiperOption" v-if="showSwiper">
    <swiper-slide v-for="item of list" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl" alt="抱歉，图片加载错误">
    </swiper-slide>
    <!-- 用来显示分页的内容 -->
    <div class="swiper-pagination" slot="pagination"></div>
  </swiper>
</div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  props: {
    list: Array
  },
  data () {
    return {
      swiperOption: {
        loop: true,
        pagination: {
          el: '.swiper-pagination',
          clickable: true
        }
      }
    }
  },
  computed: {
    showSwiper () {
      return this.list.length
    }
  }
}
</script>

<style lang='stylus' scoped>
//    >>>无视scoped的影响，进行样式穿透
  .wrapper >>> .swiper-pagination-bullet-active
    background: #fff !important
  .wrapper
      overflow:hidden
      width: 100%
      height: 31vw
      .swiper-img
          width:100%
</style>
