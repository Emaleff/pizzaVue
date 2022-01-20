<template>
  <footer class="footer">
    <div class="container footer__container">
      <div class="footer__rights">© Classic Family Restaurant</div>
      <img src="../assets/logo.png" class="footer__logo" alt="" />
      <div class="footer__made-by">
        Made with delight by
        <span class="footer__name"> harmuder </span>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: "Footer",
};
</script>

<style scoped>
.footer__container {
  padding: 33px 0 51px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.footer__rights {
  font-style: normal;
  font-weight: normal;
  font-size: 16px;
  line-height: 140%;
  color: #000000;
}
.footer__logo {
  width: 95px;
  margin-bottom: 10px;
}
.footer__made-by {
  font-style: normal;
  font-weight: normal;
  font-size: 16px;
  line-height: 140%;
  color: #000000;
}
.footer__name {
  font-family: Montserrat-Bold, sans-serif;
}
@media screen and (max-width: 650px) {
  .footer__container {
    flex-direction: column;
  }
  .footer__logo {
    margin: 25px;
  }
}
</style>
