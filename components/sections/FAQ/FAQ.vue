<template>
  <section class="w-[full] flex flex-col items-center relative">
    <div class="w-[1110px] flex gap-[90px] justify-between">
      <div class="flex flex-col gap-[30px]">
        <div class="flex flex-col gap-[10px]">
          <p class="uppercase text-sm 1.5px bg-gradient-to-r from-[#AE88FB] via-[#64B9FF] to-[#105AF6] inline-block w-fit text-transparent bg-clip-text">FAQ</p>
          <h2 class="font-semibold font-darkerGrotesque text-[65px] leading-[65px]">Frequently Asked Questions</h2>
        </div>
        <p class="leading-[140%] tracking-[1%]">Fusce pellentesque nisi commodo erat arcu quam mauris malesuada eget. Fames maecenas arcu.</p>
      </div>
      <div class="w-[575px] shrink-0 flex flex-col gap-[20px]">
        <SectionsFAQAccordion
          question-text="Fusce pellentesque nisi commodo erat arcu quam mauris ?"
          answer-text="Fusce pellentesque nisi commodo erat arcu quam mauris malesuada eget. Fames maecenas arcu habitasse sagittis dictum ac consectetur. Consequat at vel mi rutrum."
        />
        <SectionsFAQAccordion question-text="Lorem ipsum dolor sit amet ?" answer-text="Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas ut." />
        <SectionsFAQAccordion
          question-text="Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus congue, eros eu tempor placerat, purus ?"
          answer-text="Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus id elit eu tortor blandit porttitor. Proin pulvinar magna id odio vulputate blandit at cursus diam. Vestibulum viverra urna purus, vel posuere enim elementum a. Nullam vitae lacus vehicula, condimentum nibh."
        />
        <SectionsFAQAccordion
          question-text="Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque eget aliquet mi. Mauris ?"
          answer-text="Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nam dictum odio dui, nec congue felis."
        />
        <SectionsFAQAccordion
          question-text="Lorem ipsum dolor sit amet, consectetur adipiscing elit ?"
          answer-text="Fusce pellentesque nisi commodo erat arcu quam mauris malesuada eget. Fames maecenas arcu habitasse sagittis dictum ac consectetur. Consequat at vel mi rutrum."
        />
      </div>
    </div>
  </section>
</template>

<script setup lang="ts"></script>

<style scoped></style>
