<template>
  <li class="mt-16 flex flex-col items-center">
    <div
      class="w-20 h-20 flex items-center justify-center rounded-full"
      v-html="data.svg"
    ></div>

    <h1 class="mt-4 font-medium text-xl text-center">{{ data.heading }}</h1>
    <p class="mt-3 text-gray-500 text-md text-center" v-html="data.text"></p>

    <slot></slot>
  </li>
</template>

<script>
export default {
  props: {
    data: {
      type: Object,
      required: true,
    },
  },
};
</script>
