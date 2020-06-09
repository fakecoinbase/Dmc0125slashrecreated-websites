<template>
  <header class="w-full h-fc">
    <h1
      class="font-medium text-4xl text-center leading-tight tracking-wide"
    >{{ title }}</h1>
    <p
      class="mt-6 text-base text-gray-500 text-center"
    >{{ text }}</p>
  </header>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true,
    },
    text: {
      type: String,
      required: true,
    },
  },
};
</script>
