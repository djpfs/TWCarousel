<template>
  <div :class="[height ? height : '', 'w-full', 'relative', 'overflow-hidden']">
    <slot name="items"></slot>
    <div class=" w-full h-full z-30">
      <div
        @click="nextSlide()"
        class="absolute top-1/2 -mt-8 right-0 bg-gradient-to-r from-transparent to-white w-16 h-16 flex items-center justify-center text-black cursor-pointer"
      >
        &#x276F;
      </div>
      <div
        @click="previousSlide()"
        class="absolute top-1/2 -mt-8 left-0 bg-gradient-to-l from-transparent to-white w-16 h-16 mr-16  flex items-center justify-center text-black cursor-pointer"
      >
        &#x276E;
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'TWCarousel',
  props: {
    height: {
      required: false,
      type: String,
      default: 'h-64',
    },
    qtd: {
      required: false,
      type: Number,
      default: 0,
    },
  },
  data() {
    return {
      actualSlide: 0,
    }
  },
  methods: {
    nextSlide() {
      if (this.actualSlide < this.qtd - 1) {
        let activeSlide = document.querySelector('.slide.translate-x-0')
        if (activeSlide) {
          this.actualSlide++
          activeSlide.classList.remove('translate-x-0')
          activeSlide.classList.add('-translate-x-full')

          let nextSlide = activeSlide.nextElementSibling
          if (nextSlide) {
            nextSlide.classList.remove('translate-x-full')
            nextSlide.classList.add('translate-x-0')
          }
        }
      }
    },
    previousSlide() {
      if (this.actualSlide > 0) {
        let activeSlide = document.querySelector('.slide.translate-x-0')
        if (activeSlide) {
          this.actualSlide--
          activeSlide.classList.remove('translate-x-0')
          activeSlide.classList.add('translate-x-full')

          let previousSlide = activeSlide.previousElementSibling
          if (previousSlide) {
            previousSlide.classList.remove('-translate-x-full')
            previousSlide.classList.add('translate-x-0')
          }
        }
      }
    },
  },
})
</script>
