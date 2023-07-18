<template>
  <section class="Stats bg-cover bg-no-repeat bg-center relative py-8 lg:pt-32" :style="`background-image:url(${PorscheBackgroundBlue}); min-height: 300px`">
    <div class="w-full h-full bg-customBlue opacity-75 absolute top-0 left-0 z-0" />
    <div class="Stats-Components flex flex-col lg:flex-row items-center justify-between w-full z-50 relative lg:absolute px-8">
      <StatsCart v-for="obj, objIndex in cards" :key="objIndex" :content="obj"/>
    </div>
  </section>
</template>

<script>

import { reactive, toRefs } from 'vue';
import PorscheBackgroundBlue from '../assets/porsche-taycan-bluebg.jpg';
import Plug from '../assets/icons/energy.png';
import Size from '../assets/icons/box.png';
import Speed from '../assets/icons/speedometer.png'
import Weight from '../assets/icons/weight.png';
import StatsCart from './StatsCard.vue';

export default {
  components: {
    StatsCart
  },
  setup() {
    const data = reactive({
      PorscheBackgroundBlue,
      cards: [
        {
          imgSrc: Plug,
          title: "Range",
          description: "301 miles<br>(25.4 - 20.4 kWh/100 miles)"
        },
        {
          imgSrc: Speed,
          title: "Speed",
          description: "5.4s<br>0 - 100km"
        },
        {
          imgSrc: Size,
          title: "Size",
          description: "L: 4,963 mm<br>W: 1,966 mm<br>H: 1,395 mm"
        },
        {
          imgSrc: Weight,
          title: "Weight",
          description: "2,050 kg"
        }
      ]
    })

    return {
      ...toRefs(data)
    }
  }
}

</script>