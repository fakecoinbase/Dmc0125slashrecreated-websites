<template>
  <main id="app" class="w-full min-h-screen bg-white pb-8">
    <AppHeader />

    <router-view></router-view>

    <AppFooter />
  </main>
</template>

<script>
import AppHeader from '@/components/header/Header.vue';
import AppFooter from '@/components/footer/Footer.vue';

export default {
  components: {
    AppHeader,
    AppFooter,
  },
};
</script>

<style src="./assets/css/tailwind.css"></style>

<style>
* {
  transition: all 200ms ease-in-out;
}
</style>
