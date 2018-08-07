<template>
  <div>
    <SearchBar @termChange="onTermChange"></SearchBar>
    <!-- <SearchBar v-on:termChange="onTermChange"></SearchBar> -->
  </div>
</template>

<script>
import axios from 'axios';
import SearchBar from './components/SearchBar';
const API_KEY = 'AIzaSyBiN636z6nDsM-WwL0G21V12bx8UseWJHY';

export default {
  name: 'App',
  components: {
    SearchBar
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
      }).then(response => console.log(response))
    }
  }
};
</script>

<style>

</style>