<template>
  <nav class="Nav container mx-auto my-8 grid grid-flow-col grid-cols-1 gap-2">
    <div>
      <img :src="PorscheLogo" alt="Porsche logo" class="w-16 mx-auto md:mx-0"/>
    </div>
    <div class="hidden md:block">
      <div class="grid grid-flow-col grid-cols-7 gap-4 items-center h-full">
        <p
          v-for="option, optionIndex in menu"
          :key="optionIndex"
          @click="openLink(option.link)"
          class="cursor-pointer text-xs font-bold"
        >{{ option.title }}</p>
      </div>
    </div>
    <div class="block md:hidden fixed right-8 top-8">
      <img :src="MenuIcon" alt="Menu icon" class="w-12"/>
    </div>
  </nav>
</template>

<script setup>
  import PorscheLogo from '../assets/porsche-logo-bw.png';
  import MenuIcon from '../assets/icons/menu.png'

  const menu = [
    {
      title: 'Brand',
      link: ''
    },
    {
      title: '718',
      link: ''
    },
    {
      title: '911',
      link: ''
    },
    {
      title: 'Taycan',
      link: ''
    },
    {
      title: 'Macan',
      link: ''
    },
    {
      title: 'Panamera',
      link: ''
    },
    {
      title: 'Cayenne',
      link: ''
    }
  ]

  const openLink = (link) => {
    window.open(link)
  }
</script>