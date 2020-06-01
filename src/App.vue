<template>
  <div class="container">
    <div class="row" id="input">
      <SearchBar @input-search="onInputChange"/>
    </div>
    <div class="row">
      <div class="col-8" id="video">

      </div>
      <div class="col-4" id="relatedList">
        <VideoList :videos="videos" />
      </div>
    </div>
    
  </div>
</template>

<script>
import SearchBar from "./components/searchBar.vue"
import VideoList from "./components/VideoList.vue"

import axios from 'axios'

const API_KEY = 'AIzaSyAZtCqcVablP3Q8Z5fWMXr-qeLnoxPr538'
const API_URL = 'https://www.googleapis.com/youtube/v3/search'


export default {
  name: 'App',
  components: {
    SearchBar,
    VideoList,
  },
  data() {
    return {
      inputValue: '',
      videos: []
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
        }
      }).then(res => {
        this.videos = res.data.items
      }).catch(err => console.error(err))
    },
  },
}
</script>

<style>

</style>