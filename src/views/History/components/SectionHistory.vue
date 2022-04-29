<template>
  <div class="sectionHistory">
    <img class="sectionHistory__image" :src="historyData.image" alt="" />
    <h3 class="sectionHistory__title">{{ historyData.title }}</h3>
    <p class="sectionHistory__text">{{ historyData.text }}</p>
  </div>
</template>

<script>
  export default {
    name: 'SectionHistory'
  }
</script>

<script setup>
  import { defineProps, toRefs } from 'vue';

  const props = defineProps({
    historyData: JSON
  });

  const { historyData } = toRefs(props);
</script>

<style scoped>
  .sectionHistory {
    display: flex;
    text-align: center;
    flex-direction: column;
    align-items: center;
    width: 80%;
    margin-bottom: 10%;
  }
  .sectionHistory h3, p {
    font-size: calc(1rem + 6px);
  }
  .sectionHistory__image {
    width: 150px;
    height: 150px;
  }

  @media (min-width: 768px) {
    .sectionHistory {
      width: 28%;
    }
    .sectionHistory h3, p {
      font-size: calc(1rem + 10px);
    }
    .sectionHistory__image {
      transition: all .4s ease-in-out;
    }
    .sectionHistory__image:hover {
      transform: scale(1.1);
    }
  }
</style>