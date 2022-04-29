<template>
  <Navbar />
  <Header />
  <History />
  <Aspects />
  <Critics />
</template>

<script>
  import Header from './views/Header/Header.vue';
  import Navbar from './views/Navbar/Navbar.vue';
  import History from './views/History/History.vue';
  import Aspects from './views/Aspects/Aspects.vue';
  import Critics from './views/Critics/Critics.vue';

  export default {
    name: 'App',
    components: {
      Header,
      Navbar,
      History,
      Aspects,
      Critics
    }
  }
</script>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Roboto:wght@100&display=swap');

  html {
    scroll-behavior: smooth;
    font-size: 100%;
  }
  body {
    font-family: 'Roboto', sans-serif;
    box-sizing: 0;
    margin: 0;
    padding: 0;
  }
  :root {
    --dark-blue: #061D2E;
    --transition: all 0.4s ease;
  }
</style>
