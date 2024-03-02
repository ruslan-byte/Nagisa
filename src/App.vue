<template>
  <main class="px-8 bg-[url('/img/bg.jpeg')] py-10 min-h-screen">
    <VideoPlayer class="mb-12" v-if="isVideoShow"> </VideoPlayer>
    <Quest
      @hidevideo="() => (isVideoShow = false)"
      @finish="isFinishShow = true"
      v-if="!isFinishShow"
    />
    <VideoPlayer
      class="mb-12"
      :isFinish="true"
      v-if="isFinishShow"
    ></VideoPlayer>
    <Prise v-if="isFinishShow"></Prise>
  </main>
</template>
<script setup>
import VideoPlayer from "./components/VideoPlayer.vue";
import Quest from "./components/Quest.vue";
import Prise from "./components/Prise.vue";
import { ref } from "vue";
const isVideoShow = ref(true);
const isFinishShow = ref(false);
</script>
<style></style>
