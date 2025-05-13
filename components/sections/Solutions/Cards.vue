<template>
  <article class="flex gap-[125px] justify-center">
    <div class="flex flex-col gap-[45px] w-[350px]">
      <h1 class="font-semibold font-darkerGrotesque text-[45px] leading-[45px]">Do awesome card tricks !</h1>
      <SharedCTASecondary text="Try our free demo" colorScheme="lighter" link="/demo" />
    </div>
    <div class="flex flex-col gap-[30px] pt-[10px] w-[445px] shrink-0">
      <p class="tracking-[0.2px]">Fusce pellentesque nisi commodo erat arcu quam mauris malesuada eget. Fames maecenas arcu.</p>
      <div class="bg-brandLightPurple h-[261px] rounded-[10px] p-[30px]">
        <div class="h-full w-full relative">
          <img src="/imgs/presentation.png" class="absolute top-0 right-0 bg-white w-[284px] h-[178px]" />
          <img src="/imgs/dial.png" class="absolute bottom-0 left-0 bg-white w-[138px] h-[93px]" />
        </div>
      </div>
    </div>
  </article>
</template>
