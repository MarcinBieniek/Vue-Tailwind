<template>
  <section class="Presentation flex flex-col md:flex-row flex-row" :class="{ 'md:flex-row-reverse': content.left }">
    <div v-for="col, colIndex in content.columns" :key="colIndex" class="flex-1">
      <div v-if="col.imgSrc" :style="`background-image:url(${col.imgSrc}); min-height: 300px`" class="h-full bg-cover bg-center"></div>
      <div v-else class="p-8 md:p-24 " :class="`bg-${col.backgroundColor} text-${ content.left ? 'black' : 'white'}`">
        <div class="mb-12">
          <h2 class="text-4xl uppercase font-bold mb-4">{{ col.title }}</h2>
          <div class="h-2 w-16" :class="`bg-${ content.left ? 'black' : 'white'}`" />
        </div>
        <p class="uppercase font-bold mb-4">{{ col.subtitle }}</p>
        <p class="font-light" >{{ col.description }}</p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  props: {
    content: {
      default: () => {},
      type: Object
    }
  },
  setup(props) {
    props.content
  }
}

</script>