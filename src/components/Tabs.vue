<template>
  <section class="Tabs">
    <header class="flex flex-row items-center justify-center mb-4">
      <div
        v-for="obj, objIndex in tabs" :key="objIndex"
        class="Tabs-Header-Item px-6 py-4 mx-3 cursor-pointer"
        :class="objIndex === activeTab ? 'text-customBlue border-b-4 border-customBlue' : 'border-b'"
        @click="updateActiveTab(objIndex)"
      >
        {{ obj.title }}
      </div>
    </header>
    <div class="container mx-auto bg-cover bg-no-repeat flex items-center justify-center rounded-3xl" :style="`background-image:url(${getActiveTabComponent.imgSrc}); min-height: 400px`">
      <div class="mb-16 text-white flex justify-center flex-col w-full">
        <h2 class="text-4xl uppercase text-center font-bold mb-4">{{ getActiveTabComponent.title }}</h2>
        <p class="font-light px-20">{{ getActiveTabComponent.description }}</p>
      </div>
    </div>
  </section>
</template>

<script>
import { reactive, toRefs, computed } from 'vue';
import Inside from '../assets/inside.jpg';

export default {
  setup(){
    const data = reactive({
      activeTab: 0,
      getActiveTabComponent: computed(() => {
        return data.tabs[data.activeTab]
      }),
      tabs:[
        {
          imgSrc: Inside,
          title: 'Design',
          description: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum."
        },
        {
          imgSrc: Inside,
          title: 'Performance',
          description: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum."
        },
        {
          imgSrc: Inside,
          title: 'Charging',
          description: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum."
        },
        {
          imgSrc: Inside,
          title: 'Comfort',
          description: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum."
        },
      ]
    })

    const updateActiveTab = (objIndex) => {
      data.activeTab = objIndex
    }

    return {
      updateActiveTab,
      ...toRefs(data)
    }
  }
}
</script>