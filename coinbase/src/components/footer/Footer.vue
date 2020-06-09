<template>
  <footer class="max-w-290 mx-auto mt-16 px-6 md:flex">
    <header class="md:w-1/5 md:min-w-fc md:pr-4">
      <h1 class="text-blue-600 text-3xl font-medium">coinbase</h1>
      <p class="mt-4 text-gray-600 text-lg">+1 (888) 908-7930</p>
      <p>
        <a
          class="text-gray-600 text-lg hover:underline"
          href="https://support.coinbase.com"
        >support.coinbase.com
        </a>
      </p>
      <p class="mt-8 text-gray-600 text-lg">© 2019 Coinbase</p>
    </header>

    <section class="md:w-4/5 sm:flex flex-wrap justify-between">
      <ul
        class="md:min-w-fc pt-10 md:pt-0 md:pr-4 w-2/4 md:w-1/4"
        v-for="section in sections"
        :key="section.header"
      >
        <li class="mb-4 text-lg font-medium"><h3>{{ section.header }}</h3></li>
        <li
          class="text-gray-600 text-lg leading-relaxed cursor-pointer hover:underline"
          v-for="link in section.links"
          :key="link"><a href="#"
        >{{ link }}</a></li>
      </ul>
    </section>
  </footer>
</template>

<script>
export default {
  data() {
    return {
      sections: [
        {
          header: 'Products',
          links: [
            'Coinbase',
            'Commerce',
            'Custody',
            'Earn',
            'Pro',
            'USD Coin',
            'Wallet',
            'Ventures',
          ],
        },
        {
          header: 'Learn',
          links: [
            'Buy Bitcoin',
            'Buy Bitcoin Cash',
            'Buy Ethereum',
            'Buy Litecoin',
            'Buy XRP',
            'Supported countries',
            'Status',
            'Taxes',
          ],
        },
        {
          header: 'Company',
          links: [
            'About',
            'Affiliates',
            'Careers',
            'Partners',
            'Press',
            'Legal & Privacy',
            'Support',
          ],
        },
        {
          header: 'Social',
          links: [
            'Blog',
            'Twitter',
            'Facebook',
          ],
        },
      ],
    };
  },
};
</script>
