<template>
  <div class="font-outfit flex flex-col gap-[180px]">
    <Nav :colorScheme="colorScheme" />
    <SectionsHero @enter="colorScheme = 'light'" @leave="colorScheme = 'dark'" />
    <SectionsPresentation />
    <SectionsTestimonials @enter="colorScheme = 'light'" @leave="colorScheme = 'dark'" />
    <SectionsSolutions />
    <SectionsFAQ />
    <SectionsFooter @enter="colorScheme = 'light'" @leave="colorScheme = 'dark'" />
  </div>
</template>

<script setup lang="ts">
const colorScheme = ref<"light" | "dark">("light");
</script>
