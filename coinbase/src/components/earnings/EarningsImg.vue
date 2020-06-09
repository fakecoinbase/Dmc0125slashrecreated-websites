<template>
  <section class="img-bg relative md:h-fc mt-32 pb-8 md:pb-0">
    <img
      src="https://assets.coinbase.com/assets/earn-upsell-desktop.5db6c25bf65d7ea0c754859f289aeb99.jpg"
      alt="Crypto"
      class="
        absolute
        top-0
        right-0
        w-full
        sm:w-2/3
        md:w-1/2
        max-w-202
      "
    />

    <AppEarnings
      class="
        relative
        w-full
        md:w-1/2
        md:w-3/4
        max-w-290
        md:mt-0
        pt-32
        lg:px-6
        sm:pt-40
        md:py-16
        lg:py-32
      "
      :showCryptos="false"
    />
  </section>
</template>

<script>
import AppEarnings from '@/components/cryptos/Earnings.vue';

export default {
  components: {
    AppEarnings,
  },
};
</script>

<style scoped>
.img-bg {
  background-color: rgb(233, 246, 255);
}
</style>
