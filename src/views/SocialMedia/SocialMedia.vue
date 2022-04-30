<template>
  <section class="socialmedia">
    <h1 class="socialmedia__title">Redes sociales oficiales</h1>
    <div class="socialmedia__container socialmedia__container--icons">
      <a class="socialmedia__button socialmedia__button--instagram" href="https://www.instagram.com/bioshockofficial/?hl=es" target="_blank">
        <img class="socialmedia__image" src="../../assets/images/icon-instagram.png" alt="Imagen no encontrada">
      </a>
      <a class="socialmedia__button socialmedia__button--facebook" href="https://www.facebook.com/bioshock" target="_blank">
        <img class="socialmedia__image socialmedia__image--facebook" src="../../assets/images/icon-facebook.png" alt="Imagen no encontrada">
      </a>
      <a class="socialmedia__button socialmedia__button--twitter" href="https://twitter.com/bioshock" target="_blank">
        <img class="socialmedia__image socialmedia__image--twitter" src="../../assets/images/icon-twitter.png" alt="Imagen no encontrada">
      </a>
    </div>
  </section>
</template>

<script>
export default {
  name: 'SocialMedia'
}
</script>

<style scoped>
  .socialmedia {
    margin: 20% 0 30% 0;
  }
  .socialmedia__title {
    margin: 20% 0 15% 0;
    text-align: center;
    font-weight: bold;
    font-size: calc(1rem + 8px);
  }
  .socialmedia__container--icons {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: 1fr 1fr;
    justify-content: center;
  }
  .socialmedia__image {
    width: 120px;
    height: 120px;
  }
  .socialmedia__button {
    justify-self: center;
  }
  .socialmedia__button--twitter {
    grid-column: span 2;
  }

  @media (min-width: 768px) {
    .socialmedia {
      margin: 10% 0 13% 0;
    }
    .socialmedia__title {
      margin: 7% 0 5% 0;
    }
    .socialmedia__container--icons {
      display: flex;
      justify-content: space-evenly;
    }
    .socialmedia__button--twitter {
      grid-column: initial;
    }
    .socialmedia__image {
      transition: all .4s ease-in-out;
      width: 180px;
      height: 180px;
    }
    .socialmedia__image:hover {
      transform: scale(1.1);
    }
  }
</style>