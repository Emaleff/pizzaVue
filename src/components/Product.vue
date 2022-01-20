<template>
  <div class="pizza__item">
    <div v-if="product.hit" class="pizza__hit">Хіт</div>
    <img src="" alt="" class="pizza__line" />
    <img
      :src="require(`../assets/${product.img}.png`)"
      alt="product"
      class="pizza__img"
    />
    <div class="pizza__info">
      <div class="pizza__title">{{ product.title }}</div>
    </div>
    <div class="pizza__description">
      {{ product.description }}
    </div>
    <div class="pizza__price">{{ product.price }} rub</div>
    <div
      class="pizza__buy"
      @click="addCart(product.title, product.price)"
    ></div>
  </div>
</template>

<script>
export default {
  name: "Product",
  props: ["product"],
  methods: {
    addCart(title, price) {
      this.$emit("addCart", title, price);
    },
  },
};
</script>

<style scoped>
.pizza__item {
  background-size: 100% 100%;
  background-position: center;
  width: 263px;
  border: 2px solid #eceef7;
  border-radius: 15px;
  padding-bottom: 8px;
  text-align: center;
  position: relative;
}

.pizza__item::after {
  content: "";
  bottom: -48px;
  left: 50%;
  transform: translate(-50%, -50%) rotate(45deg);
  border-width: 0 2px 2px 0;
  border-radius: 0 0 15px 0;
  border-style: solid;
  border-color: #eceef6;
  position: absolute;
  background: white;
  width: 45px;
  height: 45px;
}
.pizza__line {
  display: none;
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: -1;
}
.pizza__item:hover {
  top: 3px;
}
.pizza__img {
  margin-left: auto;
  margin-right: auto;
  width: 210px;
  height: 213px;
  margin-top: 30px;
}
.pizza__info {
  max-width: 220px;
  margin-left: auto;
  margin-right: auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.pizza__title {
  font-family: Montserrat-Bold, sans-serif;
  font-style: normal;
  font-weight: 600;
  font-size: 16px;
  line-height: 140%;
  color: #000000;
  max-width: 181px;
}
.pizza__diametr {
  font-style: normal;
  font-weight: normal;
  font-size: 12px;
  line-height: 140%;
  color: #000000;
}
.pizza__description {
  max-width: 220px;
  margin-left: auto;
  margin-right: auto;
  font-style: normal;
  font-weight: normal;
  font-size: 12px;
  line-height: 140%;
  text-align: left;
  margin-top: 8px;
  color: #000000;
}
.pizza__price {
  font-style: normal;
  font-weight: 300;
  font-size: 24px;
  line-height: 140%;
  text-align: center;
  margin-top: 19px;
  color: #121146;
  padding-bottom: 70px;
}
.pizza__hit {
  position: absolute;
  top: 24px;
  left: 19px;
  display: flex;
  justify-content: center;
  align-items: center;
  font-style: normal;
  font-weight: 600;
  font-size: 12px;
  line-height: 140%;
  color: #ffffff;
  width: 60px;
  height: 25px;
  box-sizing: border-box;
  background: linear-gradient(116.88deg, #fe3326 -4.28%, #f26e0e 112.69%),
    #59aaf1;
  box-shadow: 0px 4px 8px rgba(205, 71, 41, 0.26);
  border-radius: 3px;
}
.pizza__buy {
  width: 33px;
  z-index: 1;
  /* margin-left: auto;
  margin-right: auto;
  margin-top: 18px;
  position: relative; */
  position: absolute;
  bottom: -32px;
  left: 50%;
  transform: translate(-50%, -50%);
  height: 33px;
  box-sizing: border-box;
  border-radius: 50%;
  border: 2px solid #eceef6;
}
.pizza__buy::before {
  content: url(../assets/pizza__buy.svg);
  position: absolute;
  top: 5px;
  left: 9px;
}
.pizza__buy:hover {
  background: linear-gradient(287.74deg, #f58656 8.52%, #fe5626 92.72%),
    linear-gradient(180deg, #fe5626 0%, #f23f0e 100%), #59aaf1;
  box-shadow: 0px 4px 8px rgba(205, 71, 41, 0.26);
  cursor: pointer;
}
.pizza__buy:hover::before {
  content: url(../assets/pizza__buy_hover.svg);
}
</style>
