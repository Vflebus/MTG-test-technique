<template>
  <nav
    class="fixed z-50 top-[30px] left-1/2 -translate-x-1/2 w-[1110px] h-[40px] flex items-center justify-around py-[30px] rounded-full"
    :class="{ 'text-brandWhite': colorScheme === 'light', 'text-brandBlack': colorScheme === 'dark', 'py-[30px] bg-brandBlack/5 backdrop-blur-[30px]': altStyleActive }"
  >
    <NuxtLink to="/">
      <SvgLogo class="transition-all duration-300" />
    </NuxtLink>
    <ul class="flex justify-center gap-[30px] text-sm font-[500]">
      <li class="flex justify-center items-center gap-[5px] group">
        <NavDropDown name="Your needs" :selected="tab === 'needs'" @click="toggleTab('needs')" :colorScheme="colorScheme">
          <NavDropDownItem link="/1" title="Lorem ipsum dolor" subtitle="Lorem ipsum dolor" :colorScheme="colorScheme" />
          <NavDropDownItem link="/1" title="Lorem ipsum dolor" subtitle="Lorem ipsum dolor" :colorScheme="colorScheme" />
          <NavDropDownItem link="/1" title="Lorem ipsum dolor" subtitle="Lorem ipsum dolor" :colorScheme="colorScheme" />
          <NavDropDownItem link="/1" title="Lorem ipsum dolor" subtitle="Lorem ipsum dolor" :colorScheme="colorScheme" />
        </NavDropDown>
      </li>
      <li class="flex justify-center items-center gap-[5px] group">
        <NavDropDown name="Our solutions" :selected="tab === 'solutions'" @click="toggleTab('solutions')" :colorScheme="colorScheme">
          <NavDropDownItem link="/1" title="Lorem ipsum dolor" subtitle="Lorem ipsum dolor" :colorScheme="colorScheme" />
          <NavDropDownItem link="/1" title="Lorem ipsum dolor" subtitle="Lorem ipsum dolor" :colorScheme="colorScheme" />
          <NavDropDownItem link="/1" title="Lorem ipsum dolor" subtitle="Lorem ipsum dolor" :colorScheme="colorScheme" />
          <NavDropDownItem link="/1" title="Lorem ipsum dolor" subtitle="Lorem ipsum dolor" :colorScheme="colorScheme" />
        </NavDropDown>
      </li>
      <li class="flex justify-center items-center gap-[5px] transition-all duration-300">
        <NuxtLink to="/about">About us</NuxtLink>
      </li>
      <li class="flex justify-center items-center gap-[5px]">
        <NavDropDown name="Ressources" :selected="tab === 'ressources'" @click="toggleTab('ressources')" :colorScheme="colorScheme">
          <NavDropDownItem link="/1" title="Lorem ipsum dolor" subtitle="Lorem ipsum dolor" :colorScheme="colorScheme" />
          <NavDropDownItem link="/1" title="Lorem ipsum dolor" subtitle="Lorem ipsum dolor" :colorScheme="colorScheme" />
          <NavDropDownItem link="/1" title="Lorem ipsum dolor" subtitle="Lorem ipsum dolor" :colorScheme="colorScheme" />
          <NavDropDownItem link="/1" title="Lorem ipsum dolor" subtitle="Lorem ipsum dolor" :colorScheme="colorScheme" />
        </NavDropDown>
      </li>
    </ul>
    <button
      class="py-[10px] px-[20px] border rounded-[5px] transition-all duration-500 flex justify-center items-center gap-[10px]"
      :class="colorScheme === 'light' ? 'border-brandWhite hover:bg-brandWhite hover:text-brandBlack' : 'border-brandBlack hover:bg-brandBlack hover:text-brandWhite'"
      @click="altStyleActive = !altStyleActive"
    >
      {{ altStyleActive ? "Standard nav style" : "Alt nav style" }} <Icon name="material-symbols:arrow-right-alt" />
    </button>
  </nav>
</template>

<script setup lang="ts">
interface Props {
  colorScheme: "light" | "dark";
}
defineProps<Props>();

const altStyleActive = ref(false);

type Tab = "needs" | "solutions" | "ressources" | "";
const tab = ref<Tab>("");

const toggleTab = (selectedTab: Tab) => {
  if (tab.value === selectedTab) tab.value = "";
  else if (tab.value) {
    tab.value = "";
    setTimeout(() => {
      tab.value = selectedTab;
    }, 100);
  } else tab.value = selectedTab;
};
</script>

<style scoped></style>
