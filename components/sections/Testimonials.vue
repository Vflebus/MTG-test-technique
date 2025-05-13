<template>
  <section class="w-full h-[771px] bg-brandBlack relative flex flex-col items-center text-brandWhite" ref="section">
    <div class="max-w-[1440px] h-full flex flex-col items-center justify-center gap-[90px]">
      <div class="text-center flex flex-col items-center gap-[10px]">
        <p class="uppercase text-sm 1.5px bg-gradient-to-r from-[#AE88FB] via-[#64B9FF] to-[#105AF6] inline-block text-transparent bg-clip-text">testimonials</p>
        <h2 class="font-semibold font-darkerGrotesque text-[65px] leading-[65px]">Et pharetra sed tempus nunc.</h2>
      </div>
      <div class="w-[920px] overflow-hidden flex flex-col gap-[60px]">
        <div class="flex gap-[5px] transition-all duration-300" :style="{ transform: `translateX(-${currentReviewIndex * 100}%) translateX(-${currentReviewIndex * 5}px)` }">
          <h3 v-for="reviewer in reviewers" :key="reviewer.name" class="font-darkerGrotesque font-semibold text-[45px] w-full shrink-0">” {{ reviewer.review }} “</h3>
        </div>
        <div class="pt-[20px] border-t border-t-brandGrey">
          <div class="flex justify-between">
            <div class="w-1/2 overflow-hidden">
              <div class="w-full flex transition-all duration-300" :style="{ transform: `translateX(-${currentReviewIndex * 100}%)` }">
                <div v-for="reviewer in reviewers" :key="reviewer.name" class="flex gap-[20px] w-full shrink-0">
                  <img class="h-[60px] w-[60px] object-cover rounded-[5px]" src="/imgs/reviewer1.svg" />
                  <div class="flex flex-col justify-center gap-[5px]">
                    <p class="font-semibold leading-[140%] tracking-[0.2px] uppercase">{{ reviewer.name }}</p>
                    <p class="text-sm leading-[140%]">{{ reviewer.position }}</p>
                  </div>
                </div>
              </div>
            </div>
            <div class="flex items-center gap-[10px]">
              <button
                class="h-[45px] w-[45px] rounded-full flex justify-center items-center border border-brandWhite hover:bg-brandWhite hover:text-brandBlack transition-all duration-200"
                @click="prevReview"
              >
                <Icon name="material-symbols:arrow-left-alt" />
              </button>
              <button
                class="h-[45px] w-[45px] rounded-full flex justify-center items-center border border-brandWhite hover:bg-brandWhite hover:text-brandBlack transition-all duration-200"
                @click="nextReview"
              >
                <Icon name="material-symbols:arrow-right-alt" />
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ScrollTrigger } from "gsap/ScrollTrigger";

const section = ref<HTMLTableSectionElement>();

const emit = defineEmits(["enter", "leave"]);

onMounted(() => {
  if (!section.value) return;
  ScrollTrigger.create({
    trigger: section.value,
    start: "top 5%",
    end: "top 5%",
    onEnter: () => emit("enter"),
    onEnterBack: () => emit("leave"),
  });
  ScrollTrigger.create({
    trigger: section.value,
    start: "bottom 5%",
    end: "bottom 5%",
    onEnter: () => emit("leave"),
    onEnterBack: () => emit("enter"),
  });
});

const reviewers = [
  {
    review: "Lectus tellus euismod arcu vitae vulputate est dui eu. Amet tortor posuere pulvinar libero ullamcorper. Integer eleifend semper est morbi.",
    name: "John Doe",
    position: "Head of Marketing @Make the Grade",
    pathToPic: "/imgs/reviewer1.svg",
  },
  {
    review: "I'm amazed ! This was the best investment in my career. Thank you, Logoipsum !",
    name: "Jane Dae",
    position: "CTO @Nasa",
    pathToPic: "/imgs/reviewer1.svg",
  },
  {
    review: "Vincent is a great developper, both smart and curious ! I would definitely recommend him for this position.",
    name: "His mom",
    position: "",
    pathToPic: "/imgs/reviewer1.svg",
  },
];
const currentReviewIndex = ref(0);
const nextReview = () => {
  if (currentReviewIndex.value === reviewers.length - 1) currentReviewIndex.value = 0;
  else currentReviewIndex.value += 1;
};
const prevReview = () => {
  if (currentReviewIndex.value === 0) currentReviewIndex.value = reviewers.length - 1;
  else currentReviewIndex.value -= 1;
};
</script>

<style scoped></style>
