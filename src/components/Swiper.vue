<template>
  <div class="swiper">
    <div>
      <img src="../assets/swiper1.png" class="swiper__img" alt="" />
    </div>

    <div>
      <img src="../assets/swiper2.png" class="swiper__img" alt="" />
    </div>

    <div>
      <img src="../assets/swiper3.png" class="swiper__img" alt="" />
    </div>

    <div>
      <img src="../assets/swiper4.png" class="swiper__img" alt="" />
    </div>

    <div>
      <img src="../assets/swiper5.png" class="swiper__img" alt="" />
    </div>

    <div>
      <img src="../assets/swiper6.png" class="swiper__img" alt="" />
    </div>
    <div class="swiper__popup">
      <div class="swiper__popup-container">
        <span class="swiper__text">
          Instagram:
          <a
            href="https://www.instagram.com/?hl=ru"
            target="_blank"
            class="swiper__link"
            >@classic_kovel
          </a>
        </span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Swiper",
};
</script>

<style scoped>
.swiper {
  display: flex;
  position: relative;
  justify-content: space-between;
  margin-bottom: 127px;
}
.swiper__img {
  background: linear-gradient(
    0deg,
    rgba(37, 77, 124, 0.4),
    rgba(37, 77, 124, 0.4)
  );
  margin: 0 20px;
}
.swiper__img:first-child {
  margin-left: 0;
}
.swiper__img:last-child {
  margin-right: 0;
}
.swiper__popup {
  position: absolute;
  width: 480px;
  height: 180px;
  box-sizing: border-box;
  background: linear-gradient(45.04deg, #fd9924 -51.05%, #f65b16 134.89%);
  box-shadow: 0px 70px 90px rgba(253, 55, 36, 0.2),
    0px 35px 50px rgba(253, 55, 36, 0.2), 0px 20px 25px rgba(253, 55, 36, 0.2);
  border-radius: 15px;
  padding: 20px;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
.swiper__popup-container {
  border: 2px solid rgba(255, 255, 255, 0.2);
  border-radius: 15px;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
.swiper__text {
  font-style: normal;
  font-weight: normal;
  font-size: 24px;
  /* line-height: 144px; */
  color: #ffffff;
}
.swiper__link {
  text-decoration: none;
  font-family: Montserrat-Bold, sans-serif;
  font-style: normal;
  font-weight: normal;
  font-size: 24px;
  line-height: 29px;
  text-align: center;
  color: #ffffff;
}
@media screen and (max-width: 1180px) {
  .swiper div img {
    width: 100%;
  }
}
@media screen and (max-width: 930px) {
.swiper__popup {
    width: 60%;
    height: 70%;
  }
}
@media screen and (max-width: 650px) {
  .swiper__popup {
    height: 100%;
    width: 100%;
    box-shadow: none;
    border-radius: 0;
  }
  .swiper__text,
  .swiper__link {
    font-size: 16px;
  }
}
@media screen and (max-width: 418px) {
  .swiper__popup {
    padding: 13px;
  }
}
</style>
