<template>
  <NuxtLink
    :to="link"
    class="w-fit min-w-[167px] px-[30px] py-[15px] flex items-center gap-[10px] rounded-[5px] group relative transition-all duration-500"
    :class="colorScheme === 'light' ? 'bg-gradient-to-r from-[#AE88FB] to-[#105AF6] text-brandBlack hover:text-brandWhite' : 'bg-brandBlack text-brandWhite'"
  >
    <div
      class="absolute top-0 left-0 h-full w-full rounded-[5px] group-hover:opacity-0 transition-all duration-500"
      :class="colorScheme === 'light' ? 'bg-brandWhite' : 'bg-gradient-to-r from-[#AE88FB] to-[#105AF6]'"
    ></div>
    <div class="relative">{{ text }}</div>
    <div class="w-4 h-4 overflow-hidden">
      <div class="flex transition-all duration-500 -translate-x-full group-hover:translate-x-0">
        <Icon name="material-symbols:arrow-right-alt" mode="svg" class="shrink-0" /><Icon name="material-symbols:arrow-right-alt" mode="svg" class="shrink-0" />
      </div>
    </div>
  </NuxtLink>
</template>

<script setup lang="ts">
interface Props {
  link: string;
  text: string;
  colorScheme: "dark" | "light";
}
defineProps<Props>();
</script>

<style scoped></style>
