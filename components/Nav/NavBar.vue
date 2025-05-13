<template>
  <nav
    class="z-50 top-[30px] left-1/2 -translate-x-1/2 w-[1110px] h-[40px] flex items-center justify-around py-[30px] rounded-full"
    :class="{
      'text-brandWhite': colorScheme === 'light',
      'text-brandBlack': colorScheme === 'dark',
      absolute: style === 'standard',
      fixed: style === 'moving',
      'fixed py-[30px] bg-brandBlack/5 backdrop-blur-[30px]': style === 'blurred',
    }"
  >
    <NuxtLink to="/">
      <SvgLogo class="transition-all duration-300" />
    </NuxtLink>
    <ul class="flex justify-center gap-[30px] text-sm font-[500]">
      <li class="flex justify-center items-center gap-[5px] group">
        <NavDropDown name="Your needs" :selected="tab === 'needs'" @click="toggleTab('needs')" :colorScheme="colorScheme" @unselect="tab = ''">
          <NuxtLink to="/1">
            <NavDropDownItem title="Lorem ipsum dolor" subtitle="Lorem ipsum dolor" :colorScheme="colorScheme" />
          </NuxtLink>
          <NuxtLink to="/1">
            <NavDropDownItem title="Lorem ipsum dolor" subtitle="Lorem ipsum dolor" :colorScheme="colorScheme" />
          </NuxtLink>
          <NuxtLink to="/1">
            <NavDropDownItem title="Lorem ipsum dolor" subtitle="Lorem ipsum dolor" :colorScheme="colorScheme" />
          </NuxtLink>
          <NuxtLink to="/1">
            <NavDropDownItem title="Lorem ipsum dolor" subtitle="Lorem ipsum dolor" :colorScheme="colorScheme" />
          </NuxtLink>
        </NavDropDown>
      </li>
      <li class="flex justify-center items-center gap-[5px] group">
        <NavDropDown name="Our solutions" :selected="tab === 'solutions'" @click="toggleTab('solutions')" :colorScheme="colorScheme" @unselect="tab = ''">
          <NuxtLink to="/1">
            <NavDropDownItem title="Lorem ipsum dolor" subtitle="Lorem ipsum dolor" :colorScheme="colorScheme" />
          </NuxtLink>
          <NuxtLink to="/1">
            <NavDropDownItem title="Lorem ipsum dolor" subtitle="Lorem ipsum dolor" :colorScheme="colorScheme" />
          </NuxtLink>
          <NuxtLink to="/1">
            <NavDropDownItem title="Lorem ipsum dolor" subtitle="Lorem ipsum dolor" :colorScheme="colorScheme" />
          </NuxtLink>
          <NuxtLink to="/1">
            <NavDropDownItem title="Lorem ipsum dolor" subtitle="Lorem ipsum dolor" :colorScheme="colorScheme" />
          </NuxtLink>
        </NavDropDown>
      </li>
      <li class="flex justify-center items-center gap-[5px] transition-all duration-300">
        <NuxtLink to="/about">About us</NuxtLink>
      </li>
      <li class="flex justify-center items-center gap-[5px]">
        <NavDropDown name="Navbar styling" :selected="tab === 'styling'" @click="toggleTab('styling')" :colorScheme="colorScheme" @unselect="tab = ''">
          <button @click="style = 'standard'">
            <NavDropDownItem title="Static" subtitle="Doesn't follow scrolling" :colorScheme="colorScheme" />
          </button>
          <button @click="style = 'moving'">
            <NavDropDownItem title="Moving" subtitle="Follows scrolling" :colorScheme="colorScheme" />
          </button>
          <button @click="style = 'blurred'">
            <NavDropDownItem title="Moving blurred" subtitle="Follows scroll and is easier to read" :colorScheme="colorScheme" />
          </button>
        </NavDropDown>
      </li>
    </ul>
    <NuxtLink
      to="/contact"
      class="py-[10px] px-[20px] border rounded-[5px] transition-all duration-500 flex justify-center items-center gap-[10px]"
      :class="colorScheme === 'light' ? 'border-brandWhite hover:bg-brandWhite hover:text-brandBlack' : 'border-brandBlack hover:bg-brandBlack hover:text-brandWhite'"
    >
      Contact us <Icon name="material-symbols:arrow-right-alt" />
    </NuxtLink>
  </nav>
</template>

<script setup lang="ts">
interface Props {
  colorScheme: "light" | "dark";
}
defineProps<Props>();

const style = ref<"standard" | "moving" | "blurred">("standard");

type Tab = "needs" | "solutions" | "styling" | "";
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
