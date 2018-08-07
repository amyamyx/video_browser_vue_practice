<template>
  <li class="list-group-item">
    <img :src="thumbnailsUrl" />
    <!-- <img v-bind:src="..." /> -->
    {{ video.snippet.title }}
  </li>
</template>

<script>
export default {
  name: 'VideoListItem',
  props: {
    video: Object
  },
  computed: {
    // thumbnailsUrl: function() {
    thumbnailsUrl() {
      return this.video.snippet.thumbnails.default.url;
    }
  }
};
</script>

