<template>
  <ul class="list-group">
    <li class="list-group-item" v-for="video in videos" :key="video.id.videoId">
      <VideoItem :video="video" @imageClicked="imageClicked" />
    </li>
  </ul>
</template>

<script>
import VideoItem from "./VideoItem";
import { mapGetters } from "vuex";

export default {
  name: "VideoList",
  components: {
    VideoItem,
  },
  computed: {
    ...mapGetters(["videos"]),
  },
  methods: {
    imageClicked(video) {
      this.$emit("imageClicked", video);
    },
  },
};
</script>

<style></style>
