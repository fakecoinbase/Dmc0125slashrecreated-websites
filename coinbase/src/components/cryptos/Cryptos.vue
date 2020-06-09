<template>
  <section>
    <ul class="max-w-290 mx-auto lg:-mt-48 bg-white lg:rounded lg:border lg:border-gray-200">
      <li
        class="
          w-full
          h-16
          px-10
          border-b
          border-gray-200
          hidden
          md:flex
          items-center
          justify-between
        "
      >
        <div class="flex items-center text-gray-600 text-lg">
          <p class="">#</p>
          <div class="ml-10">Name</div>
        </div>

        <div class="flex items-center text-gray-600 text-lg">
          <p class="md:w-32">Price</p>
          <p class="md:w-32">Change</p>
          <p class="w-20">Trade</p>
        </div>
      </li>
      <li
        v-for="(crypto, i) in cryptos"
        class="
          w-full
          h-20
          px-6
          md:px-10
          flex
          items-center
          justify-between
          border-gray-200
          cursor-pointer
          hover:bg-gray-100
        "
        :key="crypto.id"
        :class="[ i === 3 ? 'border-b-0' : 'border-b' ]"
      >
        <div class="flex items-center">
          <p class="hidden md:inline text-xl text-gray-600">{{ i + 1 }}</p>
          <img
            class="w-10 md:ml-10"
            :src="crypto.image_url"
            :alt="crypto.name"
          >
          <div class="ml-4">
            <h3 class="text-lg">{{ crypto.name }}</h3>
            <p class="text-gray-600 text-lg">{{ crypto.base }}</p>
          </div>
        </div>

        <div class="md:flex items-center">
          <h3 class="md:w-32 text-lg">{{ crypto.latest }}</h3>
          <p
            class="md:w-32 text-lg text-right md:text-left"
            :class="[ crypto.percent_change > 0 ? 'text-green-500' : 'text-red-600' ]"
          >{{ crypto.percent_change }}%</p>

          <button
            class="w-20 h-12 text-white hidden md:inline bg-green-500 hover:bg-green-600 rounded"
          >Buy</button>
        </div>
      </li>
    </ul>

    <AppEarnings />
  </section>
</template>

<script>
import formatToEur from '@/utils/formatToEur';

import AppEarnings from '@/components/cryptos/Earnings.vue';

export default {
  components: {
    AppEarnings,
  },
  data() {
    return {
      cryptos: [],
    };
  },
  methods: {
    async fetchCryptos() {
      const summary = await fetch('https://www.coinbase.com/api/v2/assets/summary?&base=EUR&filter=listed&include_prices=true&resolution=day');
      const info = await fetch('https://www.coinbase.com/api/v2/assets/info?&locale=en&filter=listed');

      const { data: summaryData } = await summary.json();
      const { data: infoData } = await info.json();

      const data = Array
        .from(summaryData, (_, i) => ({
          ...summaryData[i],
          ...infoData[i],
          latest: formatToEur(summaryData[i].latest),
          percent_change: parseFloat(summaryData[i].percent_change * 100).toFixed(2),
        }))
        .filter(current => (
          current.base === 'BTC'
          || current.base === 'ETH'
          || current.base === 'BCH'
          || current.base === 'LTC'
        ));

      this.cryptos = data;
    },
  },
  created() {
    this.fetchCryptos();
  },
};
</script>
