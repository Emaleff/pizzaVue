<template>
  <button class="form__item form__button" @click.prevent="">
    {{ btnText }}
    <img src="../assets/form-svg.svg" alt="" />
  </button>
</template>

<script>
export default {
  name: "Button",
  props: ["btnText"],
};
</script>

<style scoped>
.form__item {
  box-sizing: border-box;
  width: 260px;
  height: 60px;
  border-radius: 57px;
}
.form__button {
  padding: 20px 30px;
  background: linear-gradient(180deg, #fe5626 0%, #f23f0e 100%), #59aaf1;
  box-shadow: 0px 4px 8px rgba(205, 169, 41, 0.26);
  border-radius: 59px;
  border: 0;
  outline: 0;
  font-family: Montserrat-Bold, sans-serif;
  font-style: normal;
  font-weight: bold;
  font-size: 18px;
  line-height: 140%;
  color: #ffffff;
}
.form__button img {
  margin-left: 30px;
}
.form__button:hover {
  background: blue;
  cursor: pointer;
  transition: 0.5s;
}
</style>
