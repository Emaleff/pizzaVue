<template>
  <div class="wrapp">
    <div class="amount">{{ summPrice }} rub</div>
    <div class="cartSvg" @click="cartOpen">
      <img src="../assets/cart.svg" alt="" />
    </div>
  </div>
</template>

<script>
export default {
  name: "CartIcon",
  props: ["summPrice"],
  methods: {
    cartOpen() {
      this.$emit("cartOpen");
    },
  },
};
</script>

<style scoped>
.wrapp {
  width: 165px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.amount {
  width: 100px;
  height: 40px;
  background: #494444;
  color: #fff;
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 4px;
  position: relative;
}
.amount:after {
  content: "";
  height: 20px;
  width: 20px;
  position: absolute;
  background: #494444;
  top: 8px;
  right: -8px;
  transform: rotate(45deg);
}
.cartSvg {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  background: #fff;
  display: flex;
  justify-content: center;
  align-items: center;
  border: 1px solid gray;
  transition: 0.5s;
}
.cartSvg img {
  width: 30px;
  height: 30px;
}
.cartSvg:hover {
  cursor: pointer;
  background: #f1f1f1;
  transition: 0.5s;
}
</style>
