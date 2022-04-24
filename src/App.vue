<template>
  <Navbar />
  <Header />
  <History />
</template>

<script>
  import Header from './components/Header.vue';
  import Navbar from './components/Navbar.vue';
  import History from './components/History/History.vue';

  export default {
    name: 'App',
    components: {
      Header,
      Navbar,
      History
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
