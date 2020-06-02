<template>
  <li class="video_list_item" @click="onVideoSelect">
    <!-- computed에서 간소화시켜 가져옴 -->
    <img :src="thumbnailUrl" alt="">
    <hr>
  </li>
</template>

<script>
export default {
  name: 'VideoListItem',
  props: {
    video: Object,
  },
  methods: {
    onVideoSelect() {
      this.$emit('video-select', this.video)
    }
  },
  computed: {
    thumbnailUrl() {
      return this.video.snippet.thumbnails.medium.url
    }
  },
}
</script>

<style scoped>
li.video_list_item{

}

li.video_list_item:hover{
  background-color: #eee;
}
</style>