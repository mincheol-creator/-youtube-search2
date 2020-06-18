<template>
  <div id="app">
    <h1 class="text-center">Youtube Search</h1>
    <SearchBar />
    <div class="container">
      <div class="row">
        <div class="col-9">
          <VideoPlayer />
        </div>
        <div class="col-3">
          <VideoList @imageClicked="imageClicked" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import SearchBar from "./components/SearchBar.vue";
import VideoPlayer from "./components/VideoPlayer";
import VideoList from "./components/VideoList";

export default {
  name: "App",
  components: {
    SearchBar,
    VideoPlayer,
    VideoList,
  },
  methods: {
    imageClicked(video) {
      this.selectedVideo = video;
    },
  },
};
</script>
