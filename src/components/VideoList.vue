<template>
  <div>
    <ul>
      <li v-for="video in videos" :key="video.etag" class="d-block">
        <img :src="video.snippet.thumbnails.medium.url" alt="">
        <hr>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'VideoList',
  props: {
    videos: Array,
  },
}
</script>

<style>

</style>