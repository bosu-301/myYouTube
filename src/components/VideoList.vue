<template>
  <div>
    <ul>
      <videoListItem 
        @video-select="onVideoSelect"
        :video="video" 
        v-for="video in videos" 
        :key="video.etag" 
        class="d-block" 
      />
    </ul>
  </div>
</template>

<script>
import VideoListItem from "./VideoListItem.vue"

export default {
  name: 'VideoList',
  props: {
    videos: Array,
  },
  components: {
    VideoListItem,
  },
  methods: {
    onVideoSelect(selectVideo) {
      this.$emit('video-select', selectVideo)
    }
  },
}
</script>

<style>

</style>