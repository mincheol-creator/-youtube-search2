<template>
  <div>
    <img @click="imageClicked" :src="video.snippet.thumbnails.default.url" />
    <p>{{ video.snippet.title }}</p>
  </div>
</template>

<script>
export default {
  name: "VideoItem",
  props: {
    video: Object
  },
  methods: {
    imageClicked() {
      this.$emit("imageClicked", this.video);
    }
  }
};
</script>

<style>
</style>