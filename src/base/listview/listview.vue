<template>
  <scroll>
    <ul>
      <li v-for="group in data" class="list-group" ref="listGroup">
        <h2 class="list-group-title">{{group.title}}</h2>
        <ul>
          <li>
            <img class="avatar" v-lazy="itme.avatar">
            <span class="name">{{item.name}}</span>
          </li>
        </ul>

      </li>
    </ul>
    <div class="list-shortcut">
      <ul>
        <li class="item">
          {{item}}
        </li>
      </ul>
    </div>
    <div class="loading-containner">

    </div>


  </scroll>


</template>

<script type="text/ecmascript-6">
  import Scroll from 'base/scroll/scroll'
  // import {getData} from 'common/js/dom'

  export default {
    props: {
      data: {
        type: Array,
        default: []
      }
    },
    created () {
      this.probeType = 3
      this.listenScroll = true
      this.touch = {}
      this.listHeight = []
    },
    components: {
      Scroll
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus">

</style>
