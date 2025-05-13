<template>
  <NuxtLink :to="link" class="flex gap-[15px] group/item">
    <div class="h-[45px] w-[45px] bg-brandLightPurple flex justify-center items-center"><img src="/icons/cube.svg" alt="" /></div>
    <div class="flex flex-col justify-center font-[400]">
      <p class="flex gap-[10px] items-center text-sm" :class="colorScheme === 'light' ? 'text-brandBlack' : 'text-brandWhite'">
        {{ title }} <Icon name="material-symbols:arrow-right-alt" class="opacity-0 group-hover/item:opacity-100 transition-all" />
      </p>
      <p class="text-xs" :class="colorScheme === 'light' ? 'text-brandGrey' : 'text-brandWhite'">{{ subtitle }}</p>
    </div>
  </NuxtLink>
</template>

<script setup lang="ts">
interface Props {
  link: string;
  title: string;
  subtitle: string;
  colorScheme: "light" | "dark";
}
defineProps<Props>();
</script>

<style scoped></style>
