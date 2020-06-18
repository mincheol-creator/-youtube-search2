<template>
  <div>
    <input
      class="form-control"
      v-model="userInput"
      @keypress.enter="getVideos"
      type="text"
    />
  </div>
</template>

<script>
import { mapActions } from "vuex";
export default {
  name: "SearchBar",
  data() {
    return {
      userInput: "",
    };
  },
  methods: {
    ...mapActions(["getVideos"]),
    // testActions()
    onInput() {
      //axios 요청을 통해 $store.state.videos
      // App.vue에 $emit을 통해 userInput을 전달하는 함수
      this.$emit("onInput", this.userInput); //('이벤트명', '전달할 데이터')
      //VueX store에 data를 변경
      //mutations 함수 호출
      this.$store.commit("setUserInput", this.userInput);
      //this.$store.state.userInput = this.userInput;
      console.log("vuex 스토어 출력 :" + this.$store.state.userInput);
    },
  },
};
</script>

<style></style>
