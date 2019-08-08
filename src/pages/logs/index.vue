<template>
  <div>
    <swiper v-if="imgUrls.length > 0" indidator-dots="imgUrls.length > 1" :class="swiper" >
      <block v-for="(item, index) in imgUrls" :key="index" >
        <swiper-item>
          <image :src="item" mode="scaleToFill" :class="swiper-img"></image>
        </swiper-item>
      </block>
    </swiper>

    <ul class="container log-list">
      <li v-for="(log, index) in logs" :class="{ red: aa }" :key="index" class="log-item">
        <card :text="(index + 1) + ' . ' + log"></card>
      </li>
    </ul>
  </div>
</template>

<script>
import { formatTime } from '@/utils/index'
import card from '@/components/card'

export default {
  components: {
    card
  },

  data () {
    return {
      logs: [],
      imgUrls: [
        'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1554984988905&di=4445e8a9f6a8b5c15d9dbbf40de7f819&imgtype=0&src=http%3A%2F%2Fimg.yzt-tools.com%2F20190208%2Fc676e039cadd962811d8134b7ef109fb.jpg',
        'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1554984988905&di=4445e8a9f6a8b5c15d9dbbf40de7f819&imgtype=0&src=http%3A%2F%2Fimg.yzt-tools.com%2F20190208%2Fc676e039cadd962811d8134b7ef109fb.jpg',
        'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1554984988905&di=4445e8a9f6a8b5c15d9dbbf40de7f819&imgtype=0&src=http%3A%2F%2Fimg.yzt-tools.com%2F20190208%2Fc676e039cadd962811d8134b7ef109fb.jpg'
      ]
    }
  },

  created () {
    let logs
    if (mpvuePlatform === 'my') {
      logs = mpvue.getStorageSync({key: 'logs'}).data || []
    } else {
      logs = mpvue.getStorageSync('logs') || []
    }
    this.logs = logs.map(log => formatTime(new Date(log)))
  }
}
</script>

<style>
.log-list {
  display: flex;
  flex-direction: column;
  padding: 40rpx;
}

.log-item {
  margin: 10rpx;
}

.swiper {
  width: 100%;
}

image {
  width: 100%;
  height: 100%;
}
</style>
