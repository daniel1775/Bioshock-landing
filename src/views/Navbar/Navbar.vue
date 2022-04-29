<template>
  <nav class="navbar">
    <img class="navbar__logo" src="../../assets/images/logo.svg" alt="image not loaded">
    <fa class="navbar__bars" @click="toggleBars = !toggleBars" icon="bars"></fa>
    <ul :class="['navbar__items', handleToggle]">
      <li class="nav__items nav__items--home"><a href="#">INICIO</a></li>
      <li class="nav__items nav__items--synopsis"><a href="#">SINOPSIS</a></li>
      <li class="nav__items nav__items--aspects"><a href="#">ASPECTOS</a></li>
      <li class="nav__items nav__items--critics"><a href="#">CRÍTICAS</a></li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: 'Navbar'
}
</script>

<script setup>
  import { computed, ref } from 'vue';

  const toggleBars = ref(false);

  const handleToggle = computed(() => (
    {
      hide__items: !toggleBars.value,
      show__items: toggleBars.value
    }
  ));
</script>

<style scoped>
  .navbar {
    background-color: white;
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 100%;
    height: 75px;
    position: fixed;
    z-index: 2;
    border-bottom: 2px solid black;
  }
  .navbar__bars {
    font-size: calc(2rem + 10px);
    margin-right: 10px;
  }
  .navbar__logo {
    margin: 5px 0 5px 10px;
  }
  .navbar__items {
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    align-items: center;
    margin: 0;
    padding: 0;
    list-style: none;
    background-color: white;
    position: absolute;
    transition: var(--transition);
    top: 75px;
    width: 100%;
    height: calc(100vh - 75px);
  }
  .navbar__items a {
    font-size: calc(1rem + 4px);
    color: black;
    text-decoration: none;
    font-weight: bold;
  }
  .hide__items {
    transform: translateX(100%);
  }
  .show__items {
    transform: translateX(0);
  }

  @media (min-width: 768px) {
    .navbar__bars {
      display: none;
    }
    .navbar__logo {
      margin: 10px 0 10px 30px;
    }
    .navbar__items {
      flex-direction: row;
      position: static;
      width: 45%;
      height: auto;
      background-color: transparent;
    }
    .hide__items {
      transform: translateX(0);
    }
  }
</style>