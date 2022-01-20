<template>
  <div class="container main__container">
    <h1 class="main__title">Food delivery in Kovel</h1>
    <div class="main__subtitle">
      If you decide to relax or have unexpected guests, call us. We make sure
      that your vacation is comfortable, enjoyable and delicious
    </div>
  </div>
</template>

<script>
export default {
  name: "MainContent",
};
</script>

<style scoped>
.main__title {
  margin: 118px 0 18px;
  position: relative;
  z-index: 3;
  font-family: Montserrat-Bold, sans-serif;
  font-style: normal;
  font-weight: bold;
  font-size: 48px;
  line-height: 59px;
  text-align: center;
  color: #000000;
}
.main__subtitle {
  position: relative;
  z-index: 3;
  max-width: 621px;
  margin-left: auto;
  margin-right: auto;
  font-style: normal;
  font-weight: normal;
  font-size: 18px;
  line-height: 140%;
  text-align: center;
  color: #000000;
}
.main__container {
  position: relative;
  padding-bottom: 500px;
}
@media screen and (max-width: 880px) {
  .main__container {
    padding-bottom: 450px;
  }
}
@media screen and (max-width: 650px) {
  .main__container {
    padding-bottom: 300px;
  }
}
@media screen and (max-width: 418px) {
  .main__container {
    padding-bottom: 280px;
  }
}
</style>
