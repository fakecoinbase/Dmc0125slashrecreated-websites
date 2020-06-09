<template>
  <section
    class="max-w-290 mx-auto mt-4 lg:mt-8 md:px-6 xl:px-0 md:flex justify-between items-center"
  >
    <section
      class="
        w-full
        max-w-sm
        sm:w-1/3
        mx-auto
        md:mx-0
        px-6
        sm:px-0
        flex
        flex-col
        items-center
        md:items-start
        text-center
        md:text-left
      "
      :class="{ 'md:w-full': !showCryptos }"
    >
      <h2
        class="text-2xl md:text-3xl md:leading-tight font-medium"
      >Earn up to $130 worth of crypto</h2>
      <p
        class="text-sm mt-4"
      >
        Discover how specific cryptocurrencies work — and
        get a bit of each crypto to try out for yourself.
      </p>
      <button
        class="w-32 h-10 mt-4 text-sm text-white bg-blue-600 rounded hover:bg-blue-700"
      >Start earning</button>
    </section>

    <ul
      v-if="showCryptos"
      class="md:w-3/5 md:max-w-xl mt-4 md:mt-0 border-t border-gray-200 md:border-0"
    >
      <li
        v-for="crypto in earningCryptos"
        class="
          w-full
          h-18
          px-6
          flex
          items-center
          justify-between
          border-b
          border-gray-200
          md:border-0
          md:rounded-lg
          cursor-pointer
          hover:shadow-custom
        "
        :key="crypto.id"
      >
        <div class="flex items-center">
          <img
            class="w-10"
            :src="crypto.image_url"
            :alt="crypto.symbol"
          >
          <div class="ml-4 flex items-center">
            <h2 class="max-w-4 sm:max-w-full font-medium text-lg">{{ crypto.name }}</h2>
            <p class="ml-4 text-lg text-gray-500">{{ crypto.symbol }}</p>
          </div>
        </div>

        <div>
          <p class="font-medium text-green-600">Earn {{ crypto.earnings }} {{ crypto.symbol }}</p>
        </div>
      </li>
    </ul>
  </section>
</template>

<script>
export default {
  props: {
    showCryptos: {
      type: Boolean,
      default: true,
    },
  },
  data() {
    return {
      earningCryptos: [],
    };
  },
  methods: {
    async fetchCryptos() {
      const info = await fetch('https://www.coinbase.com/api/v2/assets/info?&locale=en&filter=listed');

      const { data } = await info.json();

      const earnings = {
        DAI: '$20',
        EOS: '$50',
        XLM: '$50',
        BAT: '$10',
      };

      const earningCryptos = data
        .filter(crypto => (
          crypto.symbol === 'DAI'
          || crypto.symbol === 'EOS'
          || crypto.symbol === 'XLM'
          || crypto.symbol === 'BAT'
        ))
        .map(crypto => ({
          ...crypto,
          earnings: earnings[crypto.symbol],
          name: crypto.symbol === 'BAT' ? 'BAT' : crypto.name,
        }));

      this.earningCryptos = earningCryptos;
    },
  },
  created() {
    this.fetchCryptos();
  },
};
</script>
