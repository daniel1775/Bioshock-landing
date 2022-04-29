<template>
  <div class="card">
    <div class="card__main">
      <img class="card__image" :src="cardData.image" alt="">
      <div :class="['card__degraded']" @click="toggleArrow = !toggleArrow">
        <fa icon="angle-down" />
      </div>
    </div>
    
    <div :class="['card__info', handleShowInfo]">
      <p class="card__title">{{ cardData.title }}</p>
      <p class="card__text">{{ cardData.text }}</p>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'CardAspects'
  }
</script>

<script setup>
  import { computed, defineProps, ref, toRefs } from 'vue';

  const props = defineProps({
    cardData: JSON
  });
  const { cardData } = toRefs(props);

  const toggleArrow = ref(false);

  const handleToggleArrow = computed(() => {
    
  });
  const handleShowInfo = computed(() => (
    {
      hide_info: !toggleArrow.value,
      show_info: toggleArrow.value
    }
  ));

</script>

<style scoped>
  .card {
    position: relative;
    margin-bottom: 1%;
    width: 98%;
  }
  .card__main {
    position: relative;
    z-index: 1;
  }
  .card__image {
    width: 100%;
  }
  .card__info {
    background-color: black;
    color: white;
    padding: 15px 0 15px 0;
    font-size: calc(1rem + 4px);
    z-index: 0;
  }
  .card__title, .card__text {
    margin: 20px 10px 20px 15px;
  }
  .hide_info {
    display: none;
  }
  .show_info {
    display: block;
  }
  .card__degraded {
    display: flex;
    justify-content: center;
    align-items: center;
    background: linear-gradient(to top, black 50%, rgba(17, 17, 17, 0.637), transparent);
    color: white;
    width: 100%;
    height: 20%;
    font-size: 2rem;
    position: absolute;
    bottom: 0;
  }

  @media (min-width: 768px) {
    .card, .card__main {
      width: 100%;
      height: 100%;
    }
    .card__main {
      position: static;
      z-index: 0;
    }
    .card__image {
      width: 100%;
      height: 100%;
    }
    .card__degraded {
      display: none;
    }
    /* title and text effect hover */
    .card__info {
      background-color: transparent;
      font-size: 2rem;
      position: absolute;
      top: 0;
      opacity: 0;
    }
    .hide_info {
      display: block;
    }
    .card__title {
      margin-left: -20%;
      margin-bottom: 30px;
      transition: all 0.3s;
    }
    .card__text {
      margin-top: 20%;
      font-size: calc(1rem + 12px);
      transition: all 0.4s;
    }
    .card:hover .card__info {
      opacity: 1;
    }
    .card:hover .card__image {
      transition:all .4s ease-in-out;
      filter: grayscale(100%) blur(3px);
    }
    .card:hover .card__title {
      margin-left: 15px;
    }
    .card:hover .card__text {
      margin-top: 0;
    }
  }
</style>