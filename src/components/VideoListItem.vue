<template>
  <li class="video_list_item" @click="onVideoSelect">
    <img :src="video.snippet.thumbnails.medium.url" alt="">
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
  }
}
</script>

<style scoped>
li.video_list_item{

}

li.video_list_item:hover{
  background-color: #eee;
}
</style>