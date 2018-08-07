<template>
  <div class="container">
    <SearchBar @termChange="onTermChange"></SearchBar>
    <!-- <SearchBar v-on:termChange="onTermChange"></SearchBar> -->
    <VideoList :videos="videos" ></VideoList>
    <!-- <VideoList v-bind:videos="videos" ></VideoList> -->
  </div>
</template>

<script>
import axios from 'axios';
import SearchBar from './components/SearchBar';
import VideoList from './components/VideoList';
const API_KEY = 'AIzaSyBiN636z6nDsM-WwL0G21V12bx8UseWJHY';

export default {
  name: 'App',
  components: {
    SearchBar,
    VideoList
  },
  // data() {}  ES6
  data: function() {
    return { videos: [] };
  },
  methods: {
    onTermChange: function(searchTerm) {
      axios.get('https://www.googleapis.com/youtube/v3/search', {
        params: {
          key: API_KEY,
          type: 'video',
          part: 'snippet',
          q: searchTerm
        }
      })
        .then(response => {
          this.videos = response.data.items;
        })
    }
  }
};
</script>

<style>

</style>