<template>
  <section class="flex flex-col gap-[180px] mt-[80px]" ref="section">
    <section class="w-full flex flex-col items-center relative">
      <img src="/imgs/pres-bg-pattern-right.svg" alt="" class="absolute top-0 right-0 pointer-events-none" />
      <div class="max-w-[1440px] px-[160px]">
        <div class="h-[768px]">
          <div class="h-[60px] w-[60px] bg-brandLightPurple rounded-[2px] flex justify-center items-center">
            <img src="/icons/cube.svg" alt="" class="w-[24px]" />
          </div>
          <h2 class="text-[65px] leading-[65px] font-darkerGrotesque font-semibold w-[825px]">A tortor ac ut cras hendrerit ornare. Pellentesque</h2>
          <div class="mt-[75px] flex w-full justify-between gap-[125px]">
            <div class="flex flex-col gap-[60px]">
              <p class="leading-[140%]">
                Fusce pellentesque nisi commodo erat arcu quam mauris malesuada eget. Fames maecenas arcu habitasse sagittis dictum ac consectetur. Consequat at vel mi rutrum. Fusce pellentesque nisi
                commodo erat arcu quam mauris malesuada eget. Fames maecenas arcu
              </p>
              <SharedCTAPrimary colorScheme="dark" text="Get started" link="/get-started" />
            </div>
            <div class="bg-brandLightPurple w-[540px] h-[527px] overflow-hidden rounded-[10px] flex items-center shrink-0 relative">
              <img src="/imgs/presentation.png" alt="Crazy ! This graph shows a sudden rise in kitten adoptions." class="w-[570px] absolute left-[60px] shadow-[0_0_30px_#0100260D]" />
            </div>
          </div>
        </div>
      </div>
    </section>
    <section class="w-full flex flex-col items-center relative">
      <img src="/imgs/pres-bg-pattern-left.svg" alt="" class="absolute top-0 left-0 pointer-events-none" />
      <div class="max-w-[1440px] px-[160px]">
        <div class="h-[768px] flex flex-col items-end">
          <div>
            <div class="h-[60px] w-[60px] bg-brandLightBlue rounded-[2px] flex justify-center items-center">
              <img src="/icons/cube.svg" alt="" class="w-[24px]" />
            </div>
            <h2 class="text-[65px] leading-[65px] font-darkerGrotesque font-semibold w-[825px]">Proin eget accumsan vestibulum adipiscing. Eu enim.</h2>
          </div>
          <div class="mt-[75px] flex w-full justify-between gap-[125px]">
            <div class="bg-brandLightBlue w-[540px] h-[527px] overflow-hidden rounded-[10px] flex items-center shrink-0 relative">
              <img src="/imgs/presentation.png" alt="Stunning statistics. You definitely want to be part of this business." class="w-[570px] absolute left-[60px] shadow-[0_0_30px_#0100260D]" />
            </div>
            <div class="flex flex-col gap-[60px]">
              <p class="leading-[140%]">
                Fusce pellentesque nisi commodo erat arcu quam mauris malesuada eget. Fames maecenas arcu habitasse sagittis dictum ac consectetur. Consequat at vel mi rutrum. Fusce pellentesque nisi
                commodo erat arcu quam mauris malesuada eget. Fames maecenas arcu
              </p>
              <SharedCTAPrimary colorScheme="dark" text="Get started" link="/get-started" />
            </div>
          </div>
        </div>
      </div>
    </section>
  </section>
</template>
