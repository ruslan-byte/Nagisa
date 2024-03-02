<template>
  <label class="flex items-center gap-2 cursor-pointer hover:text-pink-400">
    <input
      class="hidden"
      type="radio"
      :name="name"
      v-model="value"
      :checked="false"
    />
    <heartFillIcon
      class="w-5 h-5 fill-pink-400 inline-block"
      v-if="props.value == modelValue"
    ></heartFillIcon>
    <heartIcon class="w-5 h-5 fill-pink-400 inline-block" v-else></heartIcon>
    <slot></slot>
  </label>
</template>
<script setup>
import { computed, ref } from "vue";
import heartIcon from "./Icons/heart.vue";
import heartFillIcon from "./Icons/heart-fill.vue";
const props = defineProps({ name: String, modelValue: String, value: String });
const emit = defineEmits(["update:modelValue"]);
const checked = ref(false);
const value = computed({
  get: () => {
    props.modelValue;
  },
  set: (newVal) => {
    emit("update:modelValue", props.value);
  },
});
</script>
<style lang="scss"></style>
