<template>
  <div class="relative">
    <button class="transition-all duration-300">{{ name }} <Icon name="mdi-light:chevron-down" class="translate-y-1/4" /></button>
    <Transition>
      <div
        v-if="selected"
        class="absolute top-[calc(100%+15px)] left-1/2 -translate-x-1/2 rounded-[5px] w-[268px] min-h-6 flex flex-col gap-[15px] p-[15px] transition-all duration-300"
        :class="colorScheme === 'light' ? 'bg-brandWhite text-brandBlack' : 'bg-brandBlack text-brandWhite'"
      >
        <Icon
          name="tabler:triangle-filled"
          class="absolute top-0 -translate-y-1/2 left-1/2 -translate-x-1/2 transition-all duration-300"
          :class="colorScheme === 'light' ? 'text-brandWhite' : 'text-brandBlack'"
        />
        <slot />
      </div>
    </Transition>
  </div>
</template>

<script setup lang="ts">
interface Props {
  name: string;
  selected: boolean;
  colorScheme: "light" | "dark";
}
defineProps<Props>();
</script>

<style scoped>
.v-enter-active,
.v-leave-active {
  transition: all 0.2s ease;
}

.v-enter-from,
.v-leave-to {
  top: 100%;
  opacity: 0;
}
</style>
