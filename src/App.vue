<template>
  <TWCarousel height="h-72" :qtd="items.length">
    <template v-slot:items>
      <TWItem v-for="(item, k) in items" :data="item" :key="k"></TWItem>
    </template>
  </TWCarousel>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component'
import TWCarousel from './components/TWCarousel.vue'
import TWItem from './components/TWItem.vue'

@Options({
  components: {
    TWCarousel,
    TWItem,
  },
  data() {
    return {
      items: [
        {
          image:
            'https://dash.camarajurua.am.gov.br/wp-content/uploads/2021/09/Documento-de-2.png',
          title: 'Boas vindas',
          subtitle: 'Teste',
          opacity: '70',
          url: 'https://www.google.com',
        },
        {
          image:
            'https://dash.camarajurua.am.gov.br/wp-content/uploads/2021/09/Documento-de-1.png',
          title: 'Setembro Amarelo',
          subtitle:
            'Setembro Amarelo é uma campanha brasileira de prevenção ao suicídio, iniciada em 2015. O mês de setembro foi escolhido para a campanha porque, desde 2003, o dia 10 de setembro é o Dia Mundial de Prevenção do Suicídio.',
          opacity: '70',
          url:
            'http://camarajurua.am.gov.br/blog/post/2021/09/06/setembro-amarelo',
        },
      ],
    }
  },
})
export default class App extends Vue {}
</script>
