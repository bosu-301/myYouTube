<template>
  <div class="" style="background-color:rgb(250,250,250);">
    <div class="row w-100 mb-3" id="input">
      <SearchBar @input-search="onInputChange"/>
    </div>

    <div class="row" style="">
      <div class="col-8" id="videodetail">
        <VideoDetail :video="selectVideo"/>
      </div>
      <div class="col-4" id="videolist">
        <VideoList :videos="videos" @video-select="onVideoSelect" />
      </div>
    </div>
    
  </div>
</template>

<script>
import SearchBar from "./components/searchBar.vue"
import VideoList from "./components/VideoList.vue"
import VideoDetail from "./components/VideoDetail.vue"
import axios from 'axios'

const API_KEY = process.env.VUE_APP_YOUTUBE_API_KEY


const API_URL = 'https://www.googleapis.com/youtube/v3/search'


export default {
  name: 'App',
  components: {
    SearchBar,
    VideoList,
    VideoDetail,
  },
  data() {
    return {
      inputValue: '',
      videos: [],
      selectVideo: {},
    }
  },
  methods: {
    onInputChange(newValue) {
      console.log('인풋첸지 발생')
      this.inputValue = newValue
      // axios의 겟요청 을 유튜브 api에 날린다 참조 "https://developers.google.com/youtube/v3/docs/search/list"
      axios.get(API_URL, {
        params: {
          key: API_KEY,
          part: 'snippet',
          type: 'video',
          q: this.inputValue,
          maxResults: 10,
        }
      }).then(res => {
        this.videos = res.data.items
      }).catch(err => console.error(err))
    },
    onVideoSelect(selectVideo) {
      this.selectVideo = selectVideo
      
    },
  },
}
</script>

<style>

</style>
