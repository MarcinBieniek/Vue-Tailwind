<template>
  <section class="Stats-Card flex flex-col items-center text-black text-center bg-white p-16 mb-8 shadow-lg">
    <img class="h-16 mb-8" :src="content.imgSrc" :alt="content.title" />
    <h2 class="text-lg mb-2 font-light">{{ content.title }}</h2>
    <p class="font-bold" v-html="content.description" />
  </section>
</template>

<script>
import GeneralMixin from '../mixins/generalMixin'
export default {
  mixins: [GeneralMixin]
}
</script>

<style>
  .Stats-Card {
    width: 266px;
    height: 300px;
  }
</style>