<template>
  <kinesis-container class="main">
    <Header />
    <MainContent />
    <kinesis-element :strength="3" class="main__bigPizza">
      <img src="../assets/mainBigPizza.png" alt="" />
    </kinesis-element>
    <kinesis-element class="bg" :strength="15"> </kinesis-element>
    <img src="../assets/mainImg1.svg" alt="" class="mainImg1" />
    <img src="../assets/mainImg2.svg" alt="" class="mainImg2" />
    <img src="../assets/mainImg3.svg" alt="" class="mainImg3" />
    <img src="../assets/mainImg4.svg" alt="" class="mainImg4" />
  </kinesis-container>
</template>

<script>
import { KinesisContainer, KinesisElement } from "vue-kinesis";

import Header from "./Header.vue";
import MainContent from "./MainContent.vue";
export default {
  name: "Main",
  components: {
    Header,
    MainContent,
    KinesisContainer,
    KinesisElement,
  },
};
</script>

<style scoped>
.main {
  background: #f0f5fb;
  position: relative;
  box-sizing: border-box;
  min-height: 100vh;
  background-size: cover;
  box-sizing: border-box;
}
.main__bigPizza {
  position: absolute;
  top: 265px;
  margin-left: auto;
  margin-right: auto;
  left: 0;
  right: 0;
  width: 620px;
  height: 620px;
}
.main__bigPizza img {
  width: 100%;
  height: 100%;
}
.bg {
  position: absolute;
  width: 97%;
  height: 100%;
  top: 0;
  left: 0;
  background: url("../assets/bg.png");
  z-index: -2;
}
.mainImg1 {
  position: absolute;
  top: 144px;
  left: 30px;
}
.mainImg2 {
  right: 35px;
  bottom: 130px;
  position: absolute;
}
.mainImg3 {
  position: absolute;
  right: 25px;
  top: 50px;
}
.mainImg4 {
  position: absolute;
  left: 123px;
  bottom: 130px;
}
@media screen and (max-width: 820px) {
  .main__bigPizza {
    width: 400px;
    height: 400px;
    top: 280px;
  }
}
@media screen and (max-width: 500px) {
  .main__bigPizza {
    width: 250px;
    height: 250px;
    top: 450px;
  }
}
</style>
