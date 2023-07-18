<template>
  <div>
    <Nav />
    <MainHeader />
    <Presentation v-for="obj, objIndex in presentations" :key="objIndex" :content="obj" />
  </div>
</template>

<script>

  import {
    Nav,
    MainHeader,
    Presentation
  } from '../components'

  import { reactive, toRefs } from 'vue';
  import PorscheInterior from '../assets/taycan-interior.jpeg'
  import PorscheTaycan from '../assets/porsche-taycan.jpeg'

  export default {
    components: {
      Presentation, MainHeader, Nav
    },
    setup() {

      let data = reactive({
        presentations: [{
          left: false,
          columns:
          [
            {
              backgroundColor: 'customBlue',
              title: 'Future is now',
              subtitle: 'Taycan concept',
              description: 'The soul has many aspects, It is variable and constantly channging. When viewing the Porsche Taycan, it reveals itself by a smile that express total delight. Or by the urge for freedom at the wheel of the new Taycan Cross turismo, that holds its ground',
            },
            {
              imgSrc: PorscheInterior,
              size: 'contain'
            }
          ]
        }, {
          left: true,
          columns:
          [
            {
              backgroundColor: 'white',
              button: {
                backgroundColor: 'customBlue',
                text: 'Book a test'
              },
              title: 'Our first electric sportscar',
              subtitle: 'Taycan concept',
              description: 'The soul has many aspects, It is variable and constantly channging. When viewing the Porsche Taycan, it reveals itself by a smile that express total delight. Or by the urge for freedom at the wheel of the new Taycan Cross turismo, that holds its ground',
            },
            {
              imgSrc: PorscheTaycan,
              size: "contain"
            }
          ]
        }]
      })

      return {
        ...toRefs(data)
      }

    }
  }

</script>