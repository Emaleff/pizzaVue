<template>
  <div class="cart__item" >
    <div class="item__text">{{ product.title }}</div>
    <div class="item__wrapp">
      <div class="item__cost">{{ product.price }} rub</div>
      <div class="item__delete" @click="deleteItem(product.title)">
        <img src="../assets/close.svg" alt="" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CartItem",
  props: ["product"],
  methods: {
    deleteItem(title) {
      this.$emit("deleteItem", title);
    },
  },
};
</script>

<style scoped>
.item__wrapp {
  width: 150px;
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
</style>
