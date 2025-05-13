<template>
  <section class="w-[full] h-[768px] flex flex-col items-center relative">
    <img src="/imgs/solutions-bg-pattern.svg" alt="" class="absolute top-0 right-0 pointer-events-none" />
    <div class="w-[1027px] h-full flex flex-col items-center gap-[75px]">
      <div class="w-[920px] flex flex-col items-center gap-[10px]">
        <p class="uppercase text-sm tracking-[11%] bg-gradient-to-r from-[#AE88FB] via-[#64B9FF] to-[#105AF6] inline-block text-transparent bg-clip-text">Solutions</p>
        <h2 class="font-semibold font-darkerGrotesque text-[65px] leading-[65px] text-center">Ornare non dignissim enim lacus pretium nisi dui.</h2>
      </div>
      <div class="rounded-[15px] border-[1.5px] border-[#F5F2FD] p-[20px] pb-[60px] bg-[#FCFBFE] flex flex-col gap-[60px] relative">
        <nav class="rounded-[15px] p-[10px] bg-brandLightPurple relative">
          <div class="absolute bg-gradient-to-r from-[#AE88FB] to-[#105AF6] hover:text-brandWhite transition-all duration-300 rounded-[5px] px-[15px] py-[5px] text-transparent" :style="overlayCoords">
            _
          </div>
          <ul class="flex justify-around gap-[30px]">
            <li>
              <button
                id="cards"
                class="rounded-[5px] px-[15px] py-[5px] leading-[140%] tracking-[1%] relative transition-all duration-300"
                :class="activeTab?.id === 'cards' ? 'text-brandWhite' : 'hover:bg-gradient-to-r from-[#AE88FB] to-[#105AF6] hover:bg-clip-text hover:text-transparent'"
                @click="setActiveCard"
              >
                Cards
              </button>
            </li>
            <li>
              <button
                id="desposits"
                class="rounded-[5px] px-[15px] py-[5px] leading-[140%] tracking-[1%] relative transition-all duration-300"
                :class="activeTab?.id === 'desposits' ? 'text-brandWhite' : 'hover:bg-gradient-to-r from-[#AE88FB] to-[#105AF6] hover:bg-clip-text hover:text-transparent'"
                @click="setActiveCard"
              >
                Desposits
              </button>
            </li>
            <li>
              <button
                id="payments"
                class="rounded-[5px] px-[15px] py-[5px] leading-[140%] tracking-[1%] relative transition-all duration-300"
                :class="activeTab?.id === 'payments' ? 'text-brandWhite' : 'hover:bg-gradient-to-r from-[#AE88FB] to-[#105AF6] hover:bg-clip-text hover:text-transparent'"
                @click="setActiveCard"
              >
                Payments & Transfers
              </button>
            </li>
            <li>
              <button
                id="credit"
                ref="credit"
                class="rounded-[5px] px-[15px] py-[5px] leading-[140%] tracking-[1%] relative transition-all duration-300"
                :class="activeTab?.id === 'credit' ? 'text-brandWhite' : 'hover:bg-gradient-to-r from-[#AE88FB] to-[#105AF6] hover:bg-clip-text hover:text-transparent'"
                @click="setActiveCard"
              >
                Credit & Lending
              </button>
            </li>
            <li>
              <button
                id="data"
                class="rounded-[5px] px-[15px] py-[5px] leading-[140%] tracking-[1%] relative transition-all duration-300"
                :class="activeTab?.id === 'data' ? 'text-brandWhite' : 'hover:bg-gradient-to-r from-[#AE88FB] to-[#105AF6] hover:bg-clip-text hover:text-transparent'"
                @click="setActiveCard"
              >
                Data & Analytics
              </button>
            </li>
            <li>
              <button
                id="risk"
                class="rounded-[5px] px-[15px] py-[5px] leading-[140%] tracking-[1%] relative transition-all duration-300"
                :class="activeTab?.id === 'risk' ? 'text-brandWhite' : 'hover:bg-gradient-to-r from-[#AE88FB] to-[#105AF6] hover:bg-clip-text hover:text-transparent'"
                @click="setActiveCard"
              >
                Risk & Compliance
              </button>
            </li>
          </ul>
        </nav>
        <div class="w-full px-[33.5px]">
          <Transition mode="out-in">
            <SectionsSolutionsCredit v-if="activeTab?.id === 'credit'" />
            <SectionsSolutionsCards v-else-if="activeTab?.id === 'cards'" />
            <SectionsSolutionsDesposits v-else-if="activeTab?.id === 'desposits'" />
            <SectionsSolutionsPayments v-else-if="activeTab?.id === 'payments'" />
            <SectionsSolutionsData v-else-if="activeTab?.id === 'data'" />
            <SectionsSolutionsRisk v-else-if="activeTab?.id === 'risk'" />
          </Transition>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const credit = ref<HTMLButtonElement>();

const overlayCoords = ref({
  left: "0px",
  top: "0px",
  width: "0px",
  opacity: 100,
});

const activeTab = ref<HTMLButtonElement | undefined>(credit.value);
const setActiveCard = (e: MouseEvent) => {
  if (e.target) activeTab.value = e.target as HTMLButtonElement;
};
watch(activeTab, (newTab) => {
  if (!newTab) {
    overlayCoords.value.opacity = 0;
    return;
  }
  overlayCoords.value.left = newTab.offsetLeft + "px";
  overlayCoords.value.top = newTab.offsetTop + "px";
  overlayCoords.value.width = newTab.offsetWidth + "px";
  overlayCoords.value.opacity = 100;
});

onMounted(() => {
  if (credit.value) {
    activeTab.value = credit.value;
  }
});
</script>

<style scoped>
.v-enter-active,
.v-leave-active {
  transition: opacity 0.3s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}
</style>
