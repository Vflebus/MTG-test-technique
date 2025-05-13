<template>
  <section class="w-full bg-brandBlack relative flex flex-col items-center text-brandWhite" ref="section">
    <div class="w-[1110px] flex flex-col pt-[110px] pb-[45px] gap-[75px]">
      <div class="flex items-center justify-between gap-[120px] w-full">
        <div class="flex flex-col gap-[20px]">
          <h2 class="w-[685px] text-[65px] leading-[65px] font-darkerGrotesque font-semibold bg-gradient-to-r from-[#AE88FB] via-[#64B9FF] to-[#105AF6] inline-block text-transparent bg-clip-text">
            Vitae varius gravida amet neque eu nunc non pretium.
          </h2>
          <p class="w-[546px] tracking-[1%] leading-[140%]">Fusce pellentesque nisi commodo erat arcu quam mauris malesuada eget. Fames maecenas arcu.</p>
        </div>
        <SharedCTAPrimary text="Get Started" colorScheme="light" link="/demo" class="shrink-0" />
      </div>
      <div class="w-full h-[1px] bg-brandWhite/30"></div>
      <div class="flex flex-col gap-[90px] w-full">
        <div class="w-full flex gap-[90px] justify-between">
          <div class="flex flex-col gap-[45px] w-[255px]">
            <div class="flex flex-col gap-[20px]">
              <SvgLogo />
              <p class="tracking-[1%] leading-[140%]">Fusce pellentesque nisi commodo erat arcu quam mauris.</p>
            </div>
            <div class="flex gap-[15px]">
              <a href="https://www.linkedin.com/company/mkthgrd/?originalSubdomain=fr" target="_blank">
                <img src="/imgs/linkedin.svg" alt="" />
              </a>
              <a href="https://x.com/hubspot" target="_blank">
                <img src="/imgs/x.svg" alt="" />
              </a>
              <a href="https://www.instagram.com/mkthgrd/?hl=fr" target="_blank">
                <img src="/imgs/instagram.svg" alt="" />
              </a>
            </div>
          </div>
          <div class="flex justify-between grow">
            <div class="w-[160px] flex flex-col gap-[30px]">
              <p class="text-brandWhite/50 uppercase text-sm tracking-[11%]">Your needs</p>
              <div class="flex flex-col gap-[20px]">
                <NuxtLink to="/" class="leading-[140%] tracking-[1%]">Secure</NuxtLink>
                <NuxtLink to="/" class="leading-[140%] tracking-[1%]">Improve</NuxtLink>
                <NuxtLink to="/" class="leading-[140%] tracking-[1%]">Grow</NuxtLink>
                <NuxtLink to="/" class="leading-[140%] tracking-[1%]">Save / Manage</NuxtLink>
              </div>
            </div>
            <div class="w-[160px] flex flex-col gap-[30px]">
              <p class="text-brandWhite/50 uppercase text-sm tracking-[1.5px]">Our solutions</p>
              <div class="flex flex-col gap-[20px]">
                <NuxtLink to="/" class="leading-[140%] tracking-[1%]">Secure</NuxtLink>
                <NuxtLink to="/" class="leading-[140%] tracking-[1%]">Improve</NuxtLink>
                <NuxtLink to="/" class="leading-[140%] tracking-[1%]">Grow</NuxtLink>
                <NuxtLink to="/" class="leading-[140%] tracking-[1%]">Save / Manage</NuxtLink>
              </div>
            </div>
            <div class="w-[160px] flex flex-col gap-[30px]">
              <p class="text-brandWhite/50 uppercase text-sm tracking-[1.5px]">Ressources</p>
              <div class="flex flex-col gap-[20px]">
                <NuxtLink to="/" class="leading-[140%] tracking-[1%]">Blog</NuxtLink>
                <NuxtLink to="/" class="leading-[140%] tracking-[1%]">Case studies</NuxtLink>
                <NuxtLink to="/" class="leading-[140%] tracking-[1%]">News</NuxtLink>
              </div>
            </div>
            <div class="w-[160px] flex flex-col gap-[30px]">
              <p class="text-brandWhite text-sm tracking-[1.5px]">About us</p>
              <div class="flex flex-col gap-[20px]">
                <NuxtLink to="/" class="leading-[140%] tracking-[1%]">Contact</NuxtLink>
              </div>
            </div>
          </div>
        </div>
        <div class="w-full h-[1px] bg-brandWhite/30"></div>
        <div class="flex justify-center items-end gap-[30px] w-full">
          <NuxtLink to="/" class="tracking-[1%] leading-[140%] text-brandWhite/50">@Make the Grade 2025. All right reserved</NuxtLink>
          <NuxtLink to="/" class="tracking-[1%] leading-[140%] text-brandWhite/50">GDPR</NuxtLink>
          <NuxtLink to="/" class="tracking-[1%] leading-[140%] text-brandWhite/50">Privacy</NuxtLink>
          <NuxtLink to="/" class="tracking-[1%] leading-[140%] text-brandWhite/50">Cookie Policy</NuxtLink>
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
    start: "top 7%",
    end: "top 7%",
    onEnter: () => emit("enter"),
    onEnterBack: () => emit("leave"),
  });
});
</script>

<style scoped></style>
