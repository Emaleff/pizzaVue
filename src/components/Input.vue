<template>
  <input
    required
    type="text"
    class="form__item form__input"
    :placeholder="inputPlaceholder"
  />
</template>

<script>
export default {
  name: "Input",
  props: ["inputPlaceholder"],
};
</script>

<style scoped>
.form__item {
  box-sizing: border-box;
  width: 260px;
  height: 60px;
  border-radius: 57px;
}
.form__input {
  padding: 20px 30px;
  border: 2px solid #eceef7;
  outline: 0;
  font-style: normal;
  font-weight: normal;
  font-size: 14px;
  line-height: 140%;
  color: #222222;
}
::placeholder {
  font-family: Montserrat-Regular, sans-serif;
  font-style: normal;
  font-weight: normal;
  font-size: 14px;
  line-height: 140%;
  color: #222222;
}
@media screen and (max-width: 980px) {
  .form__item {
    margin: 10px;
  }
}
</style>
