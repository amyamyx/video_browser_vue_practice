<template>
  <ul>
    VideoList
  </ul>
</template>

<script>
import VideoListItem from './VideoListItem';

export default {
  name: 'VideoList',
  components: {
    VideoListItem
  },
  // props: ['videos']
  props: {
    videos: Array
  }
};
</script>

<style>
</style>
