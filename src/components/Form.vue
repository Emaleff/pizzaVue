<template>
  <kinesis-container class="form-block">
    <div class="container form-block__container">
      <div class="form-block__title">
        Fill out the form and we will call you
      </div>
      <form class="form">
        <Input :inputPlaceholder="'Your name'" />
        <Input :inputPlaceholder="'Phone number'" />
        <Button :btnText="'Call back'" />
      </form>
      <img src="../assets/car.png" class="form-block__car" alt="" />
    </div>
    <kinesis-element class="bgForm" :strength="4"> </kinesis-element>
    <img src="../assets/formImg1.svg" class="formImg1" alt="" />
    <img src="../assets/formImg2.svg" class="formImg2" alt="" />
    <img src="../assets/formImg3.svg" class="formImg3" alt="" />
  </kinesis-container>
</template>

<script>
import { KinesisContainer, KinesisElement } from "vue-kinesis";
import Input from "./Input.vue";
import Button from "./Button.vue";
export default {
  name: "Form",
  components: {
    KinesisContainer,
    KinesisElement,
    Input,
    Button,
  },
};
</script>

<style scoped>
.form-block {
  background: #f0f5fb;
  background-size: cover;
  background-position: bottom;
  background-repeat: no-repeat;
  position: relative;
  overflow: hidden;
}
.bgForm {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: url("../assets/bgForm.png");
  background-size: cover;
  z-index: -1;
}
.form-block__container {
  padding: 82px 0 282px;
  position: relative;
  text-align: center;
}
.form-block__title {
  font-family: Montserrat-Bold, sans-serif;
  max-width: 505px;
  margin-bottom: 42px;
  font-style: normal;
  font-weight: bold;
  font-size: 48px;
  line-height: 150%;
  margin-left: auto;
  margin-right: auto;
  text-align: center;
  color: #000000;
}
.form {
  width: 860px;
  margin-left: auto;
  margin-right: auto;
  display: flex;
  justify-content: space-between;
}
.form-block__car {
  position: absolute;
  height: auto;
  width: auto;
  top: 500px;
  left: 50%;
  transform: translate(-50%, -50%);
}
.formImg1 {
  position: absolute;
  left: 0;
  bottom: 52px;
}
.formImg2 {
  position: absolute;
  bottom: 16px;
  right: 118px;
}
.formImg3 {
  position: absolute;
  right: 63px;
  bottom: 207px;
}

@media screen and (max-width: 930px) {
  .form {
    width: 100%;
    flex-direction: column;
    align-items: center;
  }
  .form__item {
    margin: 10px;
  }
  .form-block__car {
    top: 678px;
  }
}
@media screen and (max-width: 675px) {
  .form-block__car {
    width: 500px;
    top: 707px;
  }
}
@media screen and (max-width: 575px) {
  .form-block__car {
    width: 500px;
    top: 723px;
  }
  .form-block__title {
    max-width: 80%;
    font-size: 42px;
    line-height: 125%;
  }
}
@media screen and (max-width: 510px) {
  .form-block__car {
    width: 300px;
    top: 755px;
  }
}
@media screen and (max-width: 418px) {
  .form-block__car {
    width: 300px;
    top: 755px;
  }
}
@media screen and (max-width: 366px) {
  .form-block__car {
    width: 300px;
    top: 807px;
  }
}
</style>
