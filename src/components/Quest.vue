<template>
  <section class="max-w-[760px] mx-auto">
    <button
      class="px-4 py-2 bg-pink-400 rounded-lg text-white hover:bg-pink-500 active:bg-pink-600 mx-auto block"
      @click="
        () => {
          isShow = true;
          emit('hidevideo');
        }
      "
      v-if="!isShow"
    >
      Викторина
    </button>
    <div v-if="isShow">
      <div class="bg-white px-10 py-6 rounded-xl mb-8">
        <h3 class="text-2xl mb-4">Кто сделал первый шаг в наших отношениях</h3>
        <RadioButton
          value="you"
          v-model="answers.one"
          name="quest-1"
          class="mb-2"
        >
          Ты (Настя)
        </RadioButton>
        <RadioButton value="i" v-model="answers.one" name="quest-1" class="mb-2"
          >Я (Руся)</RadioButton
        >
        <RadioButton value="Azdart" v-model="answers.one" name="quest-1"
          >АЗДАРТ</RadioButton
        >
      </div>
      <div
        class="bg-white px-10 py-6 rounded-xl mb-8"
        v-if="answers.one == 'you'"
      >
        <h3 class="text-2xl mb-4">Каким словом я называл наши отношения</h3>

        <RadioButton
          value="game"
          v-model="answers.two"
          name="quest-2"
          class="mb-2"
          >Игра</RadioButton
        >
        <RadioButton
          value="finish"
          v-model="answers.two"
          name="quest-2"
          class="mb-2"
          >Наконец-то</RadioButton
        >
        <RadioButton value="adv" v-model="answers.two" name="quest-2"
          >Приключение</RadioButton
        >
        <RadioButton value="vika" v-model="answers.two" name="quest-2"
          >Вика</RadioButton
        >
      </div>
      <div
        class="bg-white px-10 py-6 rounded-xl mb-8"
        v-if="answers.two == 'finish'"
      >
        <h3 class="text-2xl mb-4">Наш первый мем</h3>
        <RadioButton
          value="tom"
          v-model="answers.three"
          name="quest-3"
          class="mb-2"
          >ТООМ</RadioButton
        >
        <RadioButton
          value="chipi"
          v-model="answers.three"
          name="quest-3"
          class="mb-2"
          >Чипи чипи</RadioButton
        >
        <RadioButton
          value="sex"
          v-model="answers.three"
          @click="emit('finish')"
          name="quest-3"
          >мекит мекит фастер фастер</RadioButton
        >
      </div>
    </div>
  </section>
</template>
<script setup>
import { ref } from "vue";
import RadioButton from "./RadioButton.vue";
const isShow = ref(false);
const emit = defineEmits(["hidevideo", "finish"]);
const answers = ref({
  one: "",
  two: "",
  three: "",
});
</script>
<style lang="scss"></style>
