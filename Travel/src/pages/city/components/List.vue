<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-topbottom">当前城市</div>
          <div class="button-list">
            <div>
              <div class="button-wrapper ">
                <div class="button">北京</div>
              </div>
              <div class="button-wrapper ">
                <div class="button">北京</div>
              </div>
              <div class="button-wrapper ">
                <div class="button">北京</div>
              </div>
              <div class="button-wrapper ">
                <div class="button">北京</div>
              </div>
              <div class="button-wrapper ">
              <div class="button">北京</div>
            </div>
          </div>
        </div>
    </div>
        <div class="area">
      <div class="title border-topbottom">城市</div>
        <div class="button-list">
          <div>
            <div class="button-wrapper ">
              <div class="button">北京</div>
            </div>
            <div class="button-wrapper ">
              <div class="button">北京</div>
            </div>
            <div class="button-wrapper ">
              <div class="button">北京</div>
            </div>
            <div class="button-wrapper ">
              <div class="button">北京</div>
            </div>
            <div class="button-wrapper ">
            <div class="button">北京</div>
          </div>
        </div>
      </div>
    </div>
    <div class="area">
      <div class="title border-topbottom">A</div>
        <div class="item-list">
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿拉尔</div>
        </div>
        <div class="title border-topbottom">A</div>
        <div class="item-list">
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿拉尔</div>
        </div>
    </div>
  </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'
export default {
  name: 'CityList',
  mounted () {
    this.scroll = new Bscroll(this.$refs.wrapper)
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .border-topbottom
    &:before
      border-color: #ccc
    &:after
      border-color: #ccc
  .border-bottom
    &:before
      border-color: #ccc
  .list
    overflow: hidden
    line-height: .44rem
    padding-left: .2rem
    // background: #eee
    color: #666
    font-size: .26rem
    .button-list
      overflow: hidden
      padding: .1rem .6rem .1rem .1rem
      .button-wrapper
        float: left
        width: 33.33%
        .button
          padding: .1rem 0
          text-align: center
          margin : .1rem
          border: .02rem solid #ccc
          border-radius: .06rem
          color: $bgColor
    .item-list
      .item
        line-height: .76rem
        color: #666
        padding-left: .2rem
</style>
