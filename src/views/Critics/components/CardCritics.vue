<template>
  <div :class="['card', assingColor]">
    <div class="card__header">
      <h3 class="card__title">{{ cardData.title }}</h3>
      <h3 class="card__score">{{ cardData.score}}</h3>
    </div>
    <p class="card__text">
      {{ cardData.text }}
    </p>
  </div>
</template>

<script>
export default {
  name: 'CardCritics'
}
</script>

<script setup>
  import { computed, defineProps, toRefs } from 'vue';

  const props = defineProps({
    cardData: JSON,
    cardId: Number
  });
  const { cardData, cardId } = toRefs(props);

  const assingColor = computed(() => (
    {
      card_bg__dark: cardId.value%2===0,
      card_bg__blue: cardId.value%2===1
    }
  ));
</script>

<style scoped>
  .card {
    padding: 0 20px 0 20px;
  }
  .card_bg__dark {
    background-color: black;
  }
  .card_bg__blue {
    background-color: var(--dark-blue);
  }
  .card__header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin: 10% 0 10% 0;
  }
  .card__title, .card__text {
    font-size: calc(1rem + 4px);
    color: white;
  }
  .card__title {
    margin: 0 0 0 10px;
  }
  .card__text {
    margin: 10% 0 10% 0;
  }
  .card__score {
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 70%;
    width: 50px;
    height: 50px;
    background-color: white;
    color: black;
    margin: 0 15px 0 0;
  }
  
  @media (min-width: 768px) {
    .card {
      width: 25%;
      border-radius: 10px;
      transition: all .4s ease-in-out;
    }
    /* hover effect on all card */
    .card:hover {
      background-color: white;
      border: 1px solid black;
      transform: scale(1.1);
    }
    .card h3, p{
      transition: all .4s ease-in-out;
    }
    .card:hover .card__title {
      color: black;
    }
    .card:hover .card__score {
      color: white;
      background-color: black;
    }
    .card:hover .card__text {
      color: black;
    }
  }
</style>