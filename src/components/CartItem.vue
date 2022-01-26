<template>
  <div class="cart__item">
    <div class="item__text">{{ product.title }}</div>
    <div class="item__wrapp">
      <div class="item__count">
        <div>Кол-во</div>
        <span class="bold">
          <img
            src="../assets/minus.svg"
            class="item__img"
            :class="{ disabled: onChangeDisabled }"
            alt=""
            @click="minusCount(product.title, product.count)"
          />
          {{ product.count }}
          <img
            src="../assets/plus.svg"
            class="item__img"
            alt=""
            @click="plusCount(product.title, product.count)"
          />
        </span>
      </div>
      <div class="item__cost">
        <div>Цена за шт.</div>
        <span class="bold">
          {{ product.price }}
          rub
        </span>
      </div>
      <div class="item__Allcost">
        <div>Цена</div>
        <span class="bold">
          {{ product.price * product.count }}
          rub
        </span>
      </div>
      <div class="item__delete" @click="deleteItem(product.title)">
        <img src="../assets/close.svg" alt="" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      disabled: false,
    };
  },
  name: "CartItem",
  props: {
    product: {
      type: Object,
      required: true,
    },
  },
  computed: {
    onChangeDisabled() {
      if (this.product.count === 1) {
        return true;
      } else {
        return false;
      }
    },
  },
  methods: {
    deleteItem(title) {
      this.$emit("deleteItem", title);
    },
    minusCount(title, count) {
      if (count === 1) {
        this.disabled = true;
      } else {
        this.$emit("minusCount", title);
      }
    },
    plusCount(title, count) {
      if (count === 1) {
        this.disabled = false;
      }
      this.$emit("plusCount", title);
    },
  },
};
</script>

<style scoped>
.item__text {
  font-family: Montserrat-Bold;
}
.bold {
  font-family: Montserrat-Bold;
  line-height: 2;
}
.item__wrapp {
  max-width: 330px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.item__img {
  width: 15px;
  height: 15px;
}
.item__img.item__img.disabled {
  opacity: 0.7;
}
.item__img.disabled:hover {
  cursor: auto;
  transform: none;
}
.item__img:hover {
  cursor: pointer;
  transform: scale(1.3);
}
.item__Allcost,
.item__count {
  width: 80px;
}
.item__cost {
  margin-left: auto;
  margin-right: 20px;
  margin-left: 20px;
  width: 105px;
}
.item__delete {
  height: 25px;
  width: 25px;
  display: flex;
  justify-content: center;
  align-items: center;
  border: 1px solid gray;
  border-radius: 50%;
  margin-left: 15px;
}
.item__delete:hover {
  cursor: pointer;
  background: wheat;
  transition: 0.5s;
}
@media screen and (max-width: 500px) {
  .item__text {
    margin-bottom: 15px;
  }
}
@media screen and (max-width: 400px) {
  .item__wrapp {
    flex-direction: column;
    width: 90%;
    margin: 0 auto;
    text-align: center;
    position: relative;
  }
  .item__delete {
    position: absolute;
    top: 0;
    right: 0;
  }
}
</style>
