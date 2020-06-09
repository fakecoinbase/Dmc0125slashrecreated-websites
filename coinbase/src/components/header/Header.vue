<template>
  <header class="w-full h-fc px-6 pt-4 pb-10 lg:pb-64 sm:pb-6 bg-blue-600">
    <section class="w-full max-w-290 h-fc mx-auto flex items-center justify-between">
      <section class="flex items-center">
        <h1 class="text-white text-2xl">
          <a href="https://www.coinbase.com" target="blank">coinbase</a>
        </h1>

        <ul class="hidden xl:flex items-center ml-12 text-white font-medium">
          <li class="py-2 hover:text-gray-300"><a href="#">Prices</a></li>
          <li class="relative ml-8 py-2 hover:text-gray-300">
            <a href="#" id="products">
              Products
              <!-- eslint-disable-next-line max-len -->
              <svg class="ml-2 hover:text-gray-300 inline" height="6" viewBox="0 0 10 6" width="10"><path d="M4 4l-.354.354.354.353.354-.353zM-.354.354l4 4 .708-.708-4-4zm4.708 4l4-4-.708-.708-4 4z"></path></svg>
            </a>

            <div id="products-list" class="absolute px-4 py-4 flex shadow bg-white rounded">
              <ul class="w-fc">
                <li><h3 class="text-gray-500 text-xl mb-4">For everyone</h3></li>
                <li
                  v-for="(link, i) in forEveryone"
                  class="flex items-center mb-4 px-4 cursor-pointer"
                  :key="i"
                >
                  <div
                    class="h-12 flex items-center justify-center rounded-full"
                    v-html="link.svg"
                  ></div>
                  <div class="w-64 ml-6">
                    <h4 class="text-black">{{ link.heading }}</h4>
                    <a href="#" class="font-light text-gray-600 text-sm">{{ link.text }}</a>
                  </div>
                </li>
              </ul>

              <div class="ml-8">
                <ul class="w-fc" v-for="(product, heading, i) in products" :key="i">
                  <li>
                    <h3
                      class="text-gray-500 text-xl mb-4"
                    >{{ heading.split('_').join(' ') }}</h3>
                  </li>
                  <li
                    v-for="(link, i) in product"
                    class="flex items-center mb-4 px-4 cursor-pointer"
                    :key="i"
                  >
                    <div
                      class="w-12 h-12 flex items-center justify-center rounded-full"
                      v-html="link.svg"
                    ></div>
                    <div class="w-64 ml-6">
                      <h4 class="text-black">{{ link.heading }}</h4>
                      <a href="#" class="font-light text-gray-600 text-sm">{{ link.text }}</a>
                    </div>
                  </li>
                </ul>
              </div>
            </div>
          </li>
          <li class="ml-8 py-2 hover:text-gray-300 relative">
            <a href="#" id="company">
              Company
              <svg
                class="ml-2 hover:text-gray-300 inline"
                height="6"
                viewBox="0 0 10 6"
                width="10"
              >
                <!-- eslint-disable-next-line max-len -->
                <path d="M4 4l-.354.354.354.353.354-.353zM-.354.354l4 4 .708-.708-4-4zm4.708 4l4-4-.708-.708-4 4z"></path>
              </svg>
            </a>

            <ul
              id="company-list"
              class="absolute w-32 h-fc py-2 bg-white font-light text-black rounded shadow"
            >
              <li
                v-for="li in companyList"
                class="cursor-pointer py-1 pl-2 hover:bg-gray-200"
                :key="li"
              >{{ li }}</li>
            </ul>
          </li>
          <li class="ml-8 py-2 hover:text-gray-300"><a href="#">Earn crypto</a></li>
        </ul>
      </section>

      <div class="w-fc flex items-center">
        <a
          href="#"
          class="hidden md:inline text-white hover:text-gray-300 md:font-medium"
        >Sign in</a>
        <button
          class="
            h-6
            md:h-12
            md:ml-8
            px-2
            md:px-6
            bg-blue-600
            border
            border-white
            rounded
            text-xs
            md:text-lg
            font-medium
            text-white
            hover:bg-white
            hover:text-blue-600
          "
        >Get Started</button>
        <button class="w-6 h-4 ml-8 relative xl:hidden">
          <div id="upper" class="absolute bg-white top-0 rounded-full"></div>
          <div id="mid" class="absolute bg-white rounded-full"></div>
          <div id="lower" class="absolute bg-white bottom-0 rounded-full"></div>
        </button>
      </div>
    </section>

    <section class="w-full mx-auto mt-10">
      <h1
        class="text-white font-bold text-3xl sm:text-5xl sm:leading-tight text-center leading-snug"
      >Buy and sell cryptocurrency</h1>
      <p
        class="text-white text-center text-lg mt-6 leading-relaxed"
      >Coinbase is the easiest place to buy, sell, and manage your cryptocurrency portfolio.</p>
    </section>

    <section class="mt-8 sm:px-6 sm:flex sm:items-center sm:justify-center">
      <input
        type="email"
        placeholder="Email address"
        class="appearance-none w-full sm:w-80 h-12 sm:h-16 px-6 rounded"
      >
      <button
        class="
          w-full
          sm:w-32
          h-16
          mt-3
          sm:mt-0
          sm:ml-4
          text-white
          bg-green-500
          rounded
          hover:bg-green-600
        "
      >Get started</button>
    </section>
  </header>
</template>

<script>
export default {
  data() {
    return {
      companyList: [
        'About us',
        'Blog',
        'Support',
        'Careers',
      ],
      forEveryone: [
        {
          svg: '<svg fill="none" width="40" viewBox="0 0 120 120" xmlns="http://www.w3.org/2000/svg"><path d="M60 120C26.9 120 0 93.1 0 60S26.9 0 60 0s60 26.9 60 60-26.9 60-60 60z" fill="#1652f0"></path><path d="M73.7 71.9c-3.1 3.1-7.3 4.9-11.9 4.9-9.3 0-16.9-7.6-16.9-16.9S52.5 43 61.8 43c4.7 0 8.9 1.9 11.9 4.9l9.3-9.3C77.6 33.3 70.1 30 61.8 30c-16.6 0-30 13.4-30 30s13.4 30 30 30c8.3 0 15.8-3.4 21.2-8.8z" fill="#fff"></path></svg>',
          heading: 'Coinbase',
          text: 'Buy, sell, and use cryptocurrency',
        },
        {
          svg: '<svg fill="none" width="40" viewBox="0 0 120 120" xmlns="http://www.w3.org/2000/svg"><path d="M60 120C26.9 120 0 93.1 0 60S26.9 0 60 0s60 26.9 60 60-26.9 60-60 60z" fill="#fff"></path><path d="M86.9 33H40l35.6 15.3c2.6 1.1 4.2 3.6 4.2 6.4V73h7c1.7 0 3-1.3 3-3V36c.1-1.7-1.3-3-2.9-3z" fill="#c7edfe"></path><path d="M29.9 73l9.2 4L71 90.9c2.3 1 4.9-.7 4.9-3.2V73z" fill="#56b4fc"></path><path d="M75.9 56.7c0-2.4-1.4-4.6-3.6-5.5L29.9 33v40h46z" fill="#1752ee"></path></svg>',
          heading: 'Wallet',
          text: 'Store your own cryptocurrency',
        },
        {
          svg: '<svg fill="none" width="40" viewBox="0 0 40 40" width="40" xmlns="http://www.w3.org/2000/svg"><path d="M20 40a20 20 0 1 0 0-40 20 20 0 0 0 0 40z" fill="#2775ca"></path><g fill="#fff"><path d="M25.48 23.18c0-2.917-1.775-3.9-5.209-4.371-2.537-.367-3.025-.963-3.025-2.146 0-1.184.859-1.921 2.5-1.921 1.496 0 2.359.52 2.713 1.725a.638.638 0 0 0 .604.462h1.312a.583.583 0 0 0 .588-.679c-.417-1.904-1.7-3.05-3.713-3.408v-2.008a.625.625 0 0 0-.625-.625h-1.25a.625.625 0 0 0-.625.625v1.937c-2.5.35-4.079 2-4.079 4.117 0 2.737 1.667 3.8 5.15 4.27 2.371.388 3.046.9 3.046 2.246s-1.146 2.25-2.763 2.25c-2.179 0-2.916-.954-3.162-2.191a.634.634 0 0 0-.613-.509h-1.425a.584.584 0 0 0-.579.68c.363 2.083 1.7 3.608 4.425 3.975v1.975a.625.625 0 0 0 .625.625h1.25a.625.625 0 0 0 .625-.625v-1.975c2.584-.409 4.23-2.192 4.23-4.43z"></path><path d="M15.713 31.95a12.5 12.5 0 0 1 0-23.484.9.9 0 0 0 .537-.787V6.512a.592.592 0 0 0-.833-.596 15 15 0 0 0 0 28.583.592.592 0 0 0 .833-.595v-1.167a.9.9 0 0 0-.537-.788zM24.583 5.916a.592.592 0 0 0-.833.596v1.167a.9.9 0 0 0 .537.787 12.5 12.5 0 0 1 0 23.483.833.833 0 0 0-.537.788v1.167a.592.592 0 0 0 .833.596 15 15 0 0 0 0-28.584z"></path></g></svg>',
          heading: 'USD Coin',
          text: 'Cryptocurrency with a stable price',
        },
        {
          svg: '<svg fill="none" width="40" viewBox="0 0 120 120" xmlns="http://www.w3.org/2000/svg"><path d="M60 120C26.9 120 0 93.1 0 60S26.9 0 60 0s60 26.9 60 60-26.9 60-60 60z" fill="#fff"></path><path d="M38.1 41.255v39.29h12.455V64.92h-.566l.566-.567V41.255z" fill="#b6e9ff"></path><path d="M80.9 80.545H50.557V93H80.9z" fill="#56b4fc"></path><path d="M50.555 80.545H38.1V93h12.455z" fill="#1752ee"></path><path d="M80.9 28.8H50.557v12.455H80.9z" fill="#56b4fc"></path><path d="M50.555 28.8H38.1v12.455h12.455zM75.013 64.92L62.558 52.35 50.556 64.353v.567z" fill="#1752ee"></path><path d="M50.556 64.92v-.567l-.566.567z" fill="#c1272d"></path></svg>',
          heading: 'Earn',
          text: 'Make money learning about crypto',
        },
      ],
      products: {
        'For advanced traders': [
          {
            svg: '<svg fill="none" width="40" viewBox="0 0 120 120" xmlns="http://www.w3.org/2000/svg"><path d="M60 120c33.1 0 60-26.9 60-60S93.1 0 60 0 0 26.9 0 60s26.9 60 60 60z" fill="#050f19"></path><path d="M74.7 71.9c-3.1 3.1-7.3 4.9-11.9 4.9-9.3 0-16.9-7.6-16.9-16.9S53.5 43 62.8 43c4.7 0 8.9 1.9 11.9 4.9l9.3-9.3C78.6 33.3 71.1 30 62.8 30c-16.6 0-30 13.4-30 30s13.4 30 30 30c8.3 0 15.8-3.4 21.2-8.8z" fill="#fff"></path></svg>',
            heading: 'Pro',
            text: 'Advanced cryptocurrency trading',
          },
        ],
        'For businesses': [
          {
            svg: '<svg fill="none" width="70" viewBox="0 0 120 120" xmlns="http://www.w3.org/2000/svg"><path d="M60 120C26.9 120 0 93.1 0 60S26.9 0 60 0s60 26.9 60 60-26.9 60-60 60z" fill="#fff"></path><path d="M44.1 51c0-.6 0-1.2.1-1.8C36 52.1 30.1 59.8 30.1 69c0 11.6 9.4 21 21 21 9.2 0 16.9-5.9 19.8-14.1-.6 0-1.2.1-1.8.1-13.8 0-25-11.2-25-25z" fill="#b6e9ff"></path><path d="M52.9 64.4c.8 1 1.7 1.9 2.7 2.7-.5-.4-.9-.8-1.4-1.2-.4-.5-.9-1-1.3-1.5z" fill="#b6e9ff"></path><g fill="#56b4fc"><path d="M49.8 59.2c.5 1.3 1.2 2.5 1.9 3.6.4.6.8 1.1 1.2 1.6s.9 1 1.4 1.5c-1.9-1.9-3.5-4.2-4.5-6.7zM84 36.1c-1-1-2-1.8-3.1-2.6-3.4-2.3-7.4-3.6-11.7-3.6-3.6 0-7 .9-10 2.5-2.4 1.3-4.5 3-6.2 5.1-2.7 3.2-4.4 7.3-4.7 11.7 0-.4.1-.8.1-1.2.9-.1 1.8-.2 2.8-.2 10.2 0 18.6 7.2 20.6 16.8.3 1.4.4 2.8.4 4.2 0 .9-.1 1.9-.2 2.8-.4.1-.8.1-1.2.1C81.6 71.1 90.1 62 90.1 51c0-5.8-2.3-11.1-6.1-14.9zM61 70.4c-1.3-.5-2.5-1.2-3.6-1.9 1.1.7 2.3 1.3 3.6 1.9z"></path></g><path d="M71.9 71.8c.1-.9.2-1.8.2-2.8 0-1.5-.1-2.9-.4-4.2-2-9.6-10.4-16.8-20.6-16.8-.9 0-1.9.1-2.8.2-.1.4-.1.8-.1 1.2 0 .5-.1 1.1-.1 1.6 0 2.9.6 5.7 1.7 8.2s2.6 4.8 4.5 6.7c.4.4.9.8 1.4 1.2.6.5 1.1.9 1.8 1.3 1.1.8 2.3 1.4 3.6 1.9 2.5 1.1 5.3 1.7 8.2 1.7.6 0 1.1 0 1.6-.1.3 0 .6-.1 1-.1z" fill="#1752ee"></path></svg>',
            heading: 'Commerce',
            text: 'Accept cryptocurrency payments',
          },
          {
            svg: '<svg fill="none" width="70" viewBox="0 0 120 120" xmlns="http://www.w3.org/2000/svg"><path d="M60 120c33.1 0 60-26.9 60-60S93.1 0 60 0 0 26.9 0 60s26.9 60 60 60z" fill="#fff"></path><path d="M88 24H60v12h26v23c0 13.2-21.3 28.6-23.7 30.3L60 90.9V96h28c2.2 0 4-1.8 4-4V28c0-2.2-1.8-4-4-4z" fill="#b6e9ff"></path><path d="M38 40v19c0 11.5 22 27 22 27V40z" fill="#58b2fa"></path><path d="M82 59V40H60v46s22-15.5 22-27z" fill="#1752ee"></path></svg>',
            heading: 'Custody',
            text: 'Cryptocurrency custody for institutions',
          },
          {
            svg: '<svg fill="none" width="70" viewBox="0 0 120 120" xmlns="http://www.w3.org/2000/svg"><path d="M60 120C26.9 120 0 93.1 0 60S26.9 0 60 0s60 26.9 60 60-26.9 60-60 60z" fill="#fff"></path><g fill="#c7edfe"><path d="M48.7 80.9c2.5 10 6.6 16.6 11.4 16.6s8.9-6.6 11.4-16.6c-3.6-1.2-7.4-2.8-11.4-4.9-3.9 2.1-7.8 3.7-11.4 4.9zM71.5 39.6C69.1 29.6 64.9 23 60.1 23s-8.9 6.6-11.4 16.6c3.6 1.2 7.4 2.8 11.4 4.9 4-2.1 7.8-3.7 11.4-4.9z"></path><path d="M48.7 39.6c-9.8-3.3-17.5-3.2-20.1.8-2.7 4.3 1.2 12 9.3 19.9 2.5-2.5 5.5-5 8.7-7.4.5-4.9 1.2-9.4 2.1-13.3zM82.3 60.2c-2.5 2.5-5.5 5-8.7 7.4-.4 4.8-1.1 9.3-2 13.3 9.8 3.3 17.5 3.2 20.1-.8 2.6-4.2-1.3-11.9-9.4-19.9z"></path></g><path d="M52.8 48.7c2.5-1.6 4.9-3 7.3-4.2-4-2.1-7.8-3.7-11.4-4.9-1 4-1.7 8.5-2 13.3 1.9-1.5 4-2.9 6.1-4.2zM67.4 71.8c-2.5 1.6-4.9 3-7.3 4.2 4 2.1 7.8 3.7 11.4 4.9 1-4 1.7-8.5 2-13.3-1.9 1.5-3.9 2.9-6.1 4.2z" fill="#56b4fc"></path><path d="M82.3 60.2c8.1-7.9 12-15.6 9.3-19.9-2.5-4-10.3-4-20.1-.8 1 4 1.7 8.5 2 13.3 3.3 2.5 6.3 5 8.8 7.4zM38 60.2c-8.1 7.9-12 15.6-9.3 19.9 2.5 4 10.3 4 20.1.8-1-4-1.7-8.5-2-13.3-3.4-2.4-6.3-4.9-8.8-7.4z" fill="#c7edfe"></path><path d="M67.4 48.7c2.1 1.4 4.2 2.8 6.1 4.2-.4-4.8-1.1-9.3-2-13.3-3.6 1.2-7.4 2.8-11.4 4.9 2.4 1.2 4.9 2.6 7.3 4.2zM52.8 71.8c-2.1-1.4-4.2-2.8-6.1-4.2.4 4.8 1.1 9.3 2 13.3 3.6-1.2 7.4-2.8 11.4-4.9-2.4-1.2-4.8-2.6-7.3-4.2zM73.8 60.2c0 2.5-.1 5-.3 7.4 3.3-2.4 6.2-4.9 8.7-7.4-2.5-2.5-5.5-5-8.7-7.4.2 2.4.3 4.9.3 7.4z" fill="#56b4fc"></path><path d="M46.4 60.2c0-2.5.1-5 .3-7.4-3.3 2.4-6.2 4.9-8.7 7.4 2.5 2.5 5.5 5 8.7 7.4-.2-2.3-.3-4.8-.3-7.4z" fill="#56b4fc"></path><path d="M73.6 52.9c-1.9-1.4-4-2.8-6.1-4.2-2.5-1.6-4.9-3-7.3-4.2-2.4 1.3-4.9 2.7-7.3 4.2-2.1 1.4-4.2 2.8-6.1 4.2-.2 2.4-.3 4.9-.3 7.4s.1 5 .3 7.4c1.9 1.4 4 2.8 6.1 4.2 2.5 1.6 4.9 3 7.3 4.2 2.4-1.3 4.9-2.7 7.3-4.2 2.1-1.4 4.2-2.8 6.1-4.2.2-2.4.3-4.9.3-7.4s-.2-5.1-.3-7.4z" fill="#1752ee"></path><path d="M60.1 64.9a5.1 5.1 0 1 0 0-10.2 5.1 5.1 0 0 0 0 10.2z" fill="#fff"></path></svg>',
            heading: 'Ventures',
            text: 'Raise money for your crypto startup',
          },
        ],
      },
    };
  },
};
</script>

<style scoped>
#upper,
#mid,
#lower {
  width: 100%;
  height: 0.15rem;
}

#mid {
  top: 50%;
  transform: translateY(-50%);
}

svg {
  fill: currentColor;
}

#company:hover + #company-list,
#company:focus + #company-list,
#products:hover + #products-list,
#products:focus + #products-list {
  opacity: 1;
  pointer-events: all;
  transition-delay: 0;
}

#company-list,
#products-list {
  opacity: 0;
  transform: translateX(-50%);
  left: 50%;
  top: 2.5rem;
  pointer-events: none;
  transition-delay: 300ms;
}

#company-list:hover,
#products-list:hover {
  opacity: 1;
  pointer-events: all;
}
</style>
