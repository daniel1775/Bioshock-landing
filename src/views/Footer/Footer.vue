<template>
  <footer class="footer">
    <p class="footer__text">2022 Daniel Nieto. Todos los derechos reservados</p>
  </footer>
</template>

<script>
export default {
  name: 'Footer'
}
</script>

<style scoped>
  .footer {
    background-color: black;
    color: white;
    padding: 5% 0 25% 0;
  }
  .footer__text {
    text-align: center;
    font-size: calc(1rem + 6px);
    margin: 0 10px 0 10px;
  }

  @media (min-width: 768px) {
    .footer {
      padding: 5% 0 15% 0;
    }
  }
</style>