<template>
  <section class="aspects">
    <h1 class="aspects__title">ASPECTOS</h1>
    <div class="container__cards">
      <CardAspects 
        v-for="(element, index) in cardData"
        :key="index"
        :cardData="element"
        :class="`card_${index+1}`"
      />
    </div>
  </section>
</template>

<script>
  export default {
    name: 'Aspects'
  }
</script>

<script setup>
  import { ref, computed } from 'vue';
  import CardAspects from './components/CardAspects.vue';
  import SectionHistory from '../History/components/SectionHistory.vue';

  const cardData = ref([
    {
      title: "POLÍTICA",
      text: "Un mundo utópico libre de las regulaciones gubernamentales donde cada habitante tiene derecho a crecer económica y socialmente sin rendirle cuentas a nadie.",
      image: require('@/assets/images/image-politic.png')
    },
    {
      title: "VINCULOS",
      text: "Los Big Daddy’s son personas alteradas genéticamente para sentir un deseo paternal extremo hacia las Little Sister, protegiéndolas de cualquier peligro",
      image: require('@/assets/images/image-links.png')
    },
    {
      title: "HABITANTES",
      text: "Los habitantes de Rapture fueron, en alguna vez, notables aristócratas, pero poco a poco cayeron en una suerte de locura generada por el consumo y escasez del Adam.",
      image: require('@/assets/images/image-population.png')
    },
    {
      title: "POWER UP'S",
      text: "El jugador cuenta con un amplio abanico de poderes, que van desde manipular el fuego, hasta lanzar un enjambre de abejas por las manos.",
      image: require('@/assets/images/image-power.jpg')
    },
    {
      title: "ESTÉTICA",
      text: "Bioshock cuenta con una increíble estética steampunk ambientada en la década del 50 con detalles gráficos bien trabajados como la propia ciudad o los efectos del agua.",
      image: require('@/assets/images/image-esthetic.png')
    }
  ]);

  const msg = computed(() => console.log(cardData));

</script>

<style scoped>
  .aspects__title {
    text-align: center;
    font-weight: bold;
    font-size: 2rem;
  }
  .container__cards {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  @media (min-width: 768px) {
    .aspects__title {
      font-size: calc(2rem + 5px);
      margin-bottom: 5%;
    }
    .container__cards {
      display: grid;
      grid-template-columns: 1fr 1fr;
      grid-template-rows: minmax(300px, 450px) 50px minmax(350px, 400px) minmax(450px, 600px);
      align-items: initial;
      gap: 5px 5px;
    }
    .card_1 {
      grid-row: 1/3;
      grid-column: 1/2;
    }
    .card_2 {
      grid-row: 3/4;
      grid-column: 1/2;
    }
    .card_3 {
      grid-row: 1/2;
      grid-column: 2/3;
    }
    .card_4 {
      grid-row: 2/4;
      grid-column: 2/3;
    }
    .card_5 {
      grid-row: 4;
      grid-column: 1/3;
    } 
  }
</style>