<template>
  <div class="ml-5">
    <videoPlayer v-if="video" :videoId="videoId" class="mb-4"/>
    <h5>{{video.snippet.title}}</h5>
    <br>
    <p>조회수 xx ㆍ{{ video.snippet.publishTime }}</p>
    <hr>
  </div>
</template>

<script>
import Vue from 'vue'
import VueYoutube from 'vue-youtube'
import VideoPlayer from './VideoPlayer'

Vue.use(VueYoutube)

export default {
  name: 'VideoDetail',
  components: {
    VideoPlayer,
  },
  props: {
    video: {
      type: Object,
    }
  },

  datas() {
  },
  methods: {
  },
  computed: {
    videoId() {
      return this.video.id.videoId
    },
  }
}
</script>

<style>

</style>