<template>
  <div class="rounded-[5px] p-[20px] flex gap-[30px] cursor-pointer" :class="open ? 'bg-brandBlack text-brandWhite' : 'bg-white hover:bg-brandLightBlue text-brandBlack'" @click="open = !open">
    <div
      class="flex flex-col gap-[15px] overflow-hidden transition-all duration-300"
      :style="{
        'max-height': open ? maxHeight : minHeight,
      }"
      ref="content"
    >
      <p class="font-semibold leading-[140%]" ref="question">{{ questionText }}</p>
      <p class="leading-[140%]">{{ answerText }}</p>
    </div>
    <Icon name="line-md:chevron-down" class="w-[20px] h-[20px] shrink-0 transition-all duration-300" :class="{ 'rotate-180': open }" />
  </div>
</template>

<script setup lang="ts">
interface Props {
  questionText: string;
  answerText: string;
}
defineProps<Props>();

const open = ref(false);
const content = ref<HTMLDivElement>();
const question = ref<HTMLParagraphElement>();
const currentHeight = ref();
const minHeight = ref();
const maxHeight = ref();

onMounted(() => {
  if (!content.value || !question.value) return;
  minHeight.value = question.value.offsetHeight + "px";
  maxHeight.value = content.value.offsetHeight + "px";
  console.log(maxHeight.value, minHeight.value);
});
</script>

<style scoped></style>
