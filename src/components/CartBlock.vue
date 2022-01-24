<template>
  <div class="wrapper" :class="{ isCartVisible: isCartVisible }">
    <div class="container">
      <div class="cart__header">
        <img src="../assets/logo.png" alt="" />
        <div class="cart__close" @click="cartClose">
          <img src="../assets/close.svg" alt="" />
        </div>
      </div>
      <div class="cart__items">
        <CartItem
          v-for="product in selectedProducts"
          :product="product"
          :key="product.id"
          @deleteItem="deleteItem"
          @minusCount="minusCount"
          @plusCount="plusCount"
        />
      </div>
      <div class="cart__summ">
        <span class="summ__text"> ИТОГО : </span>
        <span class="summ__value">{{ summPrice }} rub</span>
      </div>
      <form class="cart__form">
        <Input :inputPlaceholder="inputNamePlaceholder" />
        <Input :inputPlaceholder="inputNumberPlaceholder" />
        <Button :btnText="btnText" />
      </form>
    </div>
  </div>
</template>

<script>
import Input from "./Input.vue";
import Button from "./Button.vue";
import CartItem from "./CartItem.vue";
export default {
  data() {
    return {
      inputNamePlaceholder: "Ваше Имя...",
      inputNumberPlaceholder: "Введите номер телефона...",
      btnText: "Оформить",
    };
  },
  name: "CartBlock",
  props: ["isCartVisible", "selectedProducts", "summPrice"],
  components: {
    Input,
    Button,
    CartItem,
  },
  methods: {
    cartClose() {
      this.$emit("cartClose");
    },
    minusCount(title) {
      this.$emit("minusCount", title);
    },
    plusCount(title) {
      this.$emit("plusCount", title);
    },
    deleteItem(title) {
      this.$emit("deleteItem", title);
    },
  },
};
</script>

<style scoped>
.wrapper {
  transition: 1s;
  width: 0;
  z-index: -100;
  overflow: scroll;
}
.wrapper.isCartVisible {
  display: block;
  position: fixed;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  background: #f0f5fb;
  z-index: 99;
}
.cart__header {
  padding: 20px 0;
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-bottom: 1px solid gray;
}
.cart__close {
  width: 30px;
  height: 30px;
  border-radius: 50%;
  border: 1px solid gray;
  display: flex;
  justify-content: center;
  align-items: center;
}
.cart__close:hover {
  cursor: pointer;
  background: wheat;
  transition: 0.6s;
}
.cart__items {
  padding: 30px;
  overflow: auto;
}
.cart__item {
  margin: 10px auto;
  width: 95%;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.item__cost {
  margin-left: auto;
  margin-right: 30px;
}
.item__delete {
  height: 25px;
  width: 25px;
  display: flex;
  justify-content: center;
  align-items: center;
  border: 1px solid gray;
  border-radius: 50%;
}
.item__delete:hover {
  cursor: pointer;
  background: wheat;
  transition: 0.5s;
}
.cart__summ {
  padding: 30px;
  font-size: 24px;
  font-family: Montserrat-Bold;
  border-bottom: 1px solid gray;
}
.cart__form {
  padding: 30px;
  display: flex;
  justify-content: space-around;
  align-items: center;
}
@media screen and (max-width: 980px) {
  .cart__form {
    flex-direction: column;
  }
}
@media screen and (max-width: 500px) {
  .cart__item {
    flex-direction: column;
  }
}
</style>
