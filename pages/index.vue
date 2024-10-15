<template>
  <div class="h-[100vh] bg-[hsl(30,38%,92%)] flex justify-center items-center p-5">
    <div class="h-full w-full bg-[hsl(0,0%,100%)] rounded-lg md:h-[70%] md:w-[800px] md:flex ">
      <div class="md:flex-1 rounded-t-lg overflow-hidden md:rounded-l-lg">
        <img v-if="isMobile" src="/images/image-product-mobile.jpg" alt="Image Product Mobile">
        <img v-else src="/images/image-product-desktop.jpg" alt="Image Product Desktop">
      </div>
      <div class="flex flex-col p-5 md:p-7 gap-3 md:justify-between md:flex-1">
        <p class="uppercase tracking-[4px] mb-3 text-[hsl(228,12%,48%)]">
          Perfume
        </p>
        <h1 style="font-family: Fraunces;" class="text-[2.1rem] font-[700] text-[hsl(212,21%,14%)] mb-4 leading-[30px] md:w-[14rem]">
          Gabrielle Essence Eau De Parfum
        </h1>
        <p class="text-[hsl(228,12%,48%)] mb-4 font-[600] md:w-[15rem]">
          A floral, solar and voluptuous interpretation composed by Olivier Polge,
          Perfumer-Creator for the House of CHANEL.
        </p>
        <div class="flex justify-start items-center mb-4">
          <p style="font-family: Fraunces;" class="text-[2.3rem] font-[700] text-[hsl(158,36%,37%)] mr-4">
            $149.99
          </p>
          <p class="text-[hsl(228,12%,48%)] line-through">
            $169.99
          </p>
        </div>
        <div class="p-3 bg-[hsl(158,36%,37%)] text-[hsl(0,0%,100%)] flex justify-center rounded-md cursor-pointer hover:bg-[hsl(158,16%,37%)]">
          <img class="mr-3" src="/images/icon-cart.svg" alt="Icon Cart">
          <p class="font-[700]c">
            Add to Cart
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
const isMobile = ref(false)
const checkMediaQuery = () => {
  isMobile.value = window.matchMedia('(max-width: 768px)').matches
}
onMounted(() => {
  checkMediaQuery()
  window.addEventListener('resize', checkMediaQuery)
})
onBeforeUnmount(() => {
  window.removeEventListener('resize', checkMediaQuery)
})
</script>
