<template>
  <header class="header">
    <div class="header__banner">
      <img class="header__image header__image--movil" src="../assets/images/banner-movil.jpg" alt="">
      <img class="header__image header__image--desktop" src="../assets/images/banner.jpg" alt="">
      <div class="header__degraded"/>
    </div>
    <h1 class="header__title">
      SUMÉRGETE EN EL <br>MUNDO DE RAPTURE
    </h1>
    <p class="header__text">
      Andrew Ryan, un genio economista y un visionario sin precedentes,
      cansado del hostigamiento y persecución de los gobiernos y la iglesia
      hacía el individuo, construye su propia utopia en el fondo del atlantico...
      Rapture. Un lugar donde los grandes empresarios no tienen que pagar impuestos,
      donde los cientificos no se limitan por ninguna atadura moral o etica,
      un lugar donde Dios no tiene cabida.
    </p>
  </header>
</template>

<script>
export default {
  name: 'Header'
}
</script>

<style scoped>
  .header {
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: var(--dark-blue);
  }
  .header__banner {
    position: relative;
    width: 100%;
  }
  .header__image {
    width: 100%;
  }
  .header__image--desktop {
    display: none;
  }
  .header__degraded {
    position: absolute;
    width: 100%;
    height: 25%;
    bottom: 0;
    background: linear-gradient(to top, var(--dark-blue) 20%, #061d2e00);
  }
  .header h1, p{
    text-align: center;
    padding: 0 10% 0 10%;
    color: white;
  }
  .header h1 {
    font-size: calc(1rem + 10px);
    line-height: calc(100% + 20px);
  }
  .header p {
    font-size: calc(1rem + 6px);
    line-height: calc(100% + 10px);
  }

  @media (min-width: 768px) {
    .header__image--desktop {
      display: block;
    }
    .header__image--movil { 
      display: none;
    }
    .header h1 {
      font-size: 3rem;
    }
    .header p {
      font-size: 2rem;
    }
  }
</style>