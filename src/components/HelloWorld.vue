<template>
  <div>
    <TWCarousel></TWCarousel>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component'
import TWCarousel from './TWCarousel.vue'

@Options({
  props: {
    msg: String,
  },
  components: {
    TWCarousel,
  },
  methods: {},
})
export default class HelloWorld extends Vue {}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
