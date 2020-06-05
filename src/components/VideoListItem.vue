<template>
  <div class="video_list_item row pt-3" @click="onVideoSelect" style="">
    <!-- computed에서 간소화시켜 가져옴 -->
    <div class="col-7">
      <img :src="thumbnailUrl" alt="" style="width:100%;" class="">
    </div>
    <div class="col-5">
      <p class="title mb-1">{{this.video.snippet.title}}</p>
      <p class="text-secondary">{{this.video.snippet.channelTitle}}</p>
    </div>
    
    <div class="blink col-12 pt-3">
    <hr class="m-0">
    </div>
  </div>
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
div.video_list_item{

}

div.video_list_item:hover{
  background-color: #eee;
}
p.title{
  max-height: 50px;
  overflow: hidden;
  text-overflow: ellipsis;
}
</style>