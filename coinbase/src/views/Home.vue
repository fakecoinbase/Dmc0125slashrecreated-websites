<template>
  <section id="home">
    <AppCryptos />
    <AppPortfolio />
    <AppAboutPlatform />
    <AppStatistics />
    <AppGetStared />
    <AppEarningsImg />
  </section>
</template>

<script>
import AppCryptos from '@/components/cryptos/Cryptos.vue';
import AppPortfolio from '@/components/portfolio/Portfolio.vue';
import AppAboutPlatform from '@/components/about_platform/AboutPlatform.vue';
import AppStatistics from '@/components/statistics/Statistics.vue';
import AppGetStared from '@/components/get_started/GetStarted.vue';
import AppEarningsImg from '@/components/earnings/EarningsImg.vue';

export default {
  components: {
    AppCryptos,
    AppPortfolio,
    AppAboutPlatform,
    AppStatistics,
    AppGetStared,
    AppEarningsImg,
  },
};
</script>
