<template>
  <div
    @click="open(url)"
    :class="[
      data.image ? '' : 'color',
      data.url ? 'cursor-pointer' : '',
      'absolute inset-0 w-full h-ful text-white flex items-center justify-center text-5xl transition-all ease-in-out duration-1000 transform translate-x-0 slide',
    ]"
  >
    <img :src="data.image" class="w-full  bg-cover h-full" />
    <div
      :class="`absolute inset-0 w-full h-full bg-black opacity-${data.opacity}`"
    ></div>
    <span
      class="absolute top-1/2 z-10 -mt-10 text-red-600 text-7xl font-bold"
      >{{ data.title }}</span
    >
    <span
      class="absolute top-1/2 mt-10 z-10  text-red-600 text-4xl font-bold"
      >{{ data.subtitle }}</span
    >
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import { TWCarouselProps } from './../utils/Interfaces'

export default defineComponent({
  name: 'TWItem',
  props: {
    data: {
      required: true,
      type: Object<TWCarouselProps>,
      default: () => ({}),
    },
  },
  setup(props) {
    const open = (url: string) => {
      window.open(url, '_blank')
    }

    return {
      open,
      ...props,
    }
  },
})
</script>
