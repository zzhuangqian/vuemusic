<template>
<div class="recommend">
  <div ref="scroll"  class="recommend-content">
    <div class="slider-wrapper" v-if="recommends.length">
      <slider>
        <div v-for="item in recommends">
          <a v-bind:href="item.linkUrl">
            <img :src="item.picUrl">

          </a>
        </div>
      </slider>
    </div>
    <div class="recommend-list">
      <h1 class="list-title">热门歌单推荐</h1>
      <ul></ul>
    </div>
  </div>
</div>
</template>

<script type="text/ecmascript-6">
  import {getRecommend} from 'api/recommend'
  import {ERR_OK} from 'api/config'
  import Slider from 'base/slider/slider'
  export default {
    data () {
      return {
        recommends: []
      }
    },
    created () {
      this._getRecommend()
    },
    methods: {
      _getRecommend () {
        getRecommend().then((res) => {
          if (res.code === ERR_OK) {
            this.recommends = res.data.slider
          }
        }).then(() => {
        })
      }
    },
    components: {
      Slider
    }

  }
</script>

<style lang="stylus" rel="stylesheet/stylus">

</style>
