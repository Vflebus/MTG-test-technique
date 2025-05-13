<template>
  <section class="w-full h-[768px] bg-brandBlack relative flex flex-col items-center text-brandWhite" ref="section">
    <div class="max-w-[1440px] flex flex-col items-center">
      <img class="w-full h-full absolute top-0 left-0 pointer-events-none" src="/imgs/hero-background-pattern.svg" alt="" />
      <h1
        class="font-semibold text-[90px] leading-[90px] font-darkerGrotesque text-center w-[1110px] mt-[205px] bg-gradient-to-r from-[#AE88FB] via-[#64B9FF] to-[#105AF6] inline-block text-transparent bg-clip-text"
      >
        At volutpat id senectus eu erat nascetur quam. Convallis.
      </h1>
      <div class="absolute bottom-0 flex gap-[95px] translate-y-[81px]">
        <img src="/imgs/hero-example.png" alt="" class="h-[377px] w-[570px] shadow-[0_20px_30px_#0100260D]" />
        <div class="w-[445px] flex flex-col gap-[30px]">
          <p class="font-[400] leading-[140%]">
            Fusce pellentesque nisi commodo erat arcu quam mauris malesuada eget. Fames maecenas arcu habitasse sagittis dictum ac consectetur. Consequat at vel mi rutrum.
          </p>
          <div class="flex gap-[30px]">
            <SharedCTAPrimary text="Get Started" colorScheme="light" link="/get-started" />
            <SharedCTASecondary text="Try our free demo" colorScheme="light" link="/demo" />
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
    start: "bottom 5%",
    end: "bottom 5%",
    onEnter: () => emit("leave"),
    onEnterBack: () => emit("enter"),
  });
});
</script>
