<template>
  <section class="history">
    <div class="history__degraded" />
    <div class="history__options">
      <SectionHistory 
        v-for="(element, index) in historyData" 
        :key="index"
        :historyData="element"
      />
    </div>
  </section>
</template>

<script>
  export default {
    name: 'History'
  }
</script>

<script setup>
  import { ref } from 'vue';
  import SectionHistory from './components/SectionHistory.vue';
  
  const historyData = ref([
    {
      title: "ANDREW RYAN",
      text: "Una vez funda Rapture, Andrew Ryan descubre por accidente la existencia de unas babosas marinas muy particulares.",
      image: require('@/assets/images/icon-andrew.png')
    },
    {
      title: "ADAM",
      text: "A partir de la segregación de un líquido generado por las babosas, surge el ADAM, una sustancia capaz de alterar la genética humana.",
      image: require('@/assets/images/icon-adam.png')
    },
    {
      title: "BIG DADDY'S",
      text: "Debido a la escasez de ADAM en Rapture, Ryan se ve forzado a recolectarlo de cadáveres, por medio de unas niñas diseñadas para ello, llamadas Little Sister, con la compañia de sus guardaespaldas, los Big Daddy’s.",
      image: require('@/assets/images/icon-daddy.png')
    }
  ]);

</script>

<style scoped>
  .history {
    position: relative;
    width: 100%;
  }
  .history__degraded {
    position: absolute;
    height: 6%;
    width: 100%;
    background-color: var(--dark-blue);
  }
  .history__options {
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    width: 100%;
  }

  @media (min-width: 768px) {
    .history__degraded {
      height: 12%;
    }
    .history__options {
      flex-direction: row;
      align-items: flex-start;
      justify-content: space-around;
    }
  }
</style>