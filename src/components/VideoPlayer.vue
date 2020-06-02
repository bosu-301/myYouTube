<template>
<div class="iframebox">
  <iframe 
    :src="youtubeUrl" frameborder="0" 
    allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
    onload="doResize()"
    allowfullscreen
    ></iframe>
</div>
</template>
<script>

export default {
  name: 'VideoPlayer',
  props: {
    videoId: {
      type: String,
    },
    playerVars: {
      type: Object,
      default: function () {
        return { autoplay: 0 }
      }
    },
    width: {
      type: Number,
      default() {
        return window.innerWidth
      }
    },
    height: {
      type: Number,
      default() {
        return 640
      }
    }
  },
  datas() {
  },
  methods: {
  },
  computed : {
    youtubeUrl(){
      const url = 'https://www.youtube.com/embed/'
      return url + this.videoId
    }
  }
}
</script>

<style>
.iframebox {
  position: relative;
  width: 100%;
  padding-bottom: 56.25%
}
.iframebox iframe {
  position: absolute;
  width: 100%;
  height: 100%;
}
</style>