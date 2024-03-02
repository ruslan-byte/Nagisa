<template>
  <section class="mx-auto max-w-[760px] mt-12 rounded-[16px] overflow-hidden">
    <iframe
      width="100%"
      height="400"
      v-if="!isFinish"
      src="https://www.youtube.com/embed/aJgFzJyv_Rg?si=pFiDb2UAX6lqgB_Q?autoplay=1"
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
      allowfullscreen
    ></iframe>
    <iframe
      width="100%"
      height="400"
      v-if="isFinish"
      src="https://www.youtube.com/embed/NsG4UQgfuBo?si=osufMAEiJzp-ANS0"
      title="YouTube video player"
      frameborder="0"
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
      allowfullscreen
    ></iframe>
  </section>
</template>
<script setup>
const props = defineProps({ isFinish: Boolean });
</script>
<style lang="scss"></style>
