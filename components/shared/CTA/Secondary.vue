<template>
  <NuxtLink
    :to="link"
    class="flex flex-col w-fit gap-[5px] justify-center group"
    :class="colorScheme === 'light' ? 'text-brandWhite' : 'bg-gradient-to-r from-[#AE88FB] to-[#105AF6] inline-block text-transparent bg-clip-text'"
  >
    <div class="flex items-center gap-[10px]">{{ text }} &#8594;</div>
    <div class="w-full overflow-hidden">
      <div class="flex gap-[30px] -translate-x-[calc(100%+30px)] group-hover:translate-x-0 transition-all ease-linear duration-200">
        <div class="h-[1px] shrink-0 w-full" :class="colorScheme === 'light' ? 'bg-brandWhite' : 'bg-gradient-to-r from-[#AE88FB] to-[#105AF6]'"></div>
        <div class="h-[1px] shrink-0 w-full" :class="colorScheme === 'light' ? 'bg-brandWhite' : 'bg-gradient-to-r from-[#AE88FB] to-[#105AF6]'"></div>
      </div>
    </div>
  </NuxtLink>
</template>

<script setup lang="ts">
interface Props {
  link: string;
  text: string;
  colorScheme: "light" | "lighter";
}
defineProps<Props>();
</script>

<style scoped></style>
