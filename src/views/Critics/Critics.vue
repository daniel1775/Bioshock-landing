<template>
  <section class="critics">
    <h1 class="critics__title">CRÍTICAS</h1>
    <div class="container__cards">
      <CardCritics
        v-for="(element, index) in cardData"
        :key="index"
        :cardData="element"
        :cardId="index"
      />
    </div>
  </section>
</template>

<script>
export default {
  name: 'Critics'
}
</script>

<script setup>
  import { computed, ref } from 'vue';
  import CardCritics from './components/CardCritics.vue';

  const cardData = ref([
    {
      title: "EUROGAMER",
      score: 100,
      text: '"Abarca tantas formas de arte de entretenimiento de manera tan experta que es la mejor demostración hasta ahora de lo flexible que puede ser este medio".'
    },
    {
      title: "GAMESPY",
      score: 100,
      text: '"Una obra maestra absoluta que debe ser jugado por cualquier persona con el más mínimo interés en los juegos".'
    },
    {
      title: "IGN",
      score: 97,
      text: '"BioShock se erige como un ejemplo monolítico de la convergencia de un juego entretenido y una historia irresistiblemente siniestra y fascinante".'
    }
  ]);
</script>

<style scoped>
  .critics__title {
    margin: 20% 0 15% 0;
    text-align: center;
    font-weight: bold;
    font-size: 2rem;
  }
  .container__cards {
    display: flex;
    flex-wrap: wrap;
  }

  @media (min-width: 768px) {
    .critics__title {
      margin: 7% 0 5% 0;
    }
    .container__cards {
      justify-content: space-evenly;
    }
  }
</style>