<template>
    <div class="icons">
      <swiper :options="swiperOptions">
        <swiper-slide v-for="(page,index) of pages" :key="index">
          <div class="icon" v-for="item of list" :key="item.id">
            <div class="icon-img">
              <img class='icon-img-content' :src='item.imgUrl' />
            </div>
            <p class="icon-title">{{item.title}}</p>
          </div>
        </swiper-slide>
      </swiper>
    </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  props: {
    list: Array
  },
  data () {
    return {
      swiperOptions: {
        autoplay: false
      }
    }
  },
  // data () {
  //   return {
  //     iconList: [{
  //       id: '0001',
  //       imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
  //       title: '景点门票'
  //     }, {
  //       id: '0002',
  //       imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
  //       title: '一日游'
  //     }, {
  //       id: '0003',
  //       imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/4c/eac47dd8def8de02.png',
  //       title: '北京园博园'
  //     }, {
  //       id: '0004',
  //       imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/6c/9e54a8540fee0102.png',
  //       title: '故宫'
  //     }, {
  //       id: '0005',
  //       imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/6c/9e54a8540fee0102.png',
  //       title: '圆明园'
  //     }, {
  //       id: '0006',
  //       imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/67/9a1678221b8e0e02.png',
  //       title: '古水北镇'
  //     }, {
  //       id: '0007',
  //       imgUrl: 'https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/a40ee278d67000f2a29d2e20f6a029b3.png',
  //       title: '青山公园'
  //     }, {
  //       id: '0008',
  //       imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/47/c2b659e048b11602.png',
  //       title: '中国马镇'
  //     }]
  //   }
  // },
  computed: {
    pages () {
      const pages = []
      this.list.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  @import '~styles/mixins.styl'
  .icons >>> .swiper-container
    height : 0
    padding-bottom: 50%
  .icons
    margin-top : .1rem
    .icon
      position: relative
      overflow: hidden
      height : 0
      float left
      width: 25%
      padding-bottom :25%
      .icon-img
        position :absolute
        top: 0
        left: 0
        right: 0
        bottom: .44rem
        box-sizing: border-box
        padding: .1rem
        .icon-img-content
          display: block
          margin: 0 auto
          height: 100%
      .icon-title
        position: absolute
        left: 0
        right: 0
        bottom: 0
        height : .44rem
        line-height : .44rem
        text-align :center
        color: $darkTextColor
        overflow: hidden
        ellipsis()
</style>
