<template>
  <div class="container content__container">
    <div class="wrapp-cart">
      <Cart-icon
        class="cart-icon"
        :summPrice="summPrice"
        @cartOpen="cartOpen"
      />
    </div>
    <h2 class="content__title">Popular dishes</h2>
    <ul class="tabs-container">
      <li
        v-for="(tab, index) in tabs"
        :key="index"
        class="tab"
        :class="{ active: tab.condition }"
        @click="onChangeTab(tab.name)"
      >
        {{ tab.name }}
      </li>
    </ul>
    <div class="pizza__container">
      <Product
        v-for="product in activeProducts"
        :product="product"
        :key="product.title"
        @addCart="addCart"
      />
    </div>

    <div class="reload">
      <img src="../assets/reload.svg" alt="" />
    </div>
  </div>
</template>

<script>
import Product from "./Product.vue";
import CartIcon from "./CartIcon.vue";
export default {
  data() {
    return {
      tabs: [
        {
          name: "Pizza",
          condition: true,
        },
        {
          name: "Sushi",
          condition: false,
        },
        {
          name: "Salad",
          condition: false,
        },
        {
          name: "Dessert",
          condition: false,
        },
        {
          name: "Drinks",
          condition: false,
        },
      ],
    };
  },
  name: "Products",
  props: {
    activeProducts: {
      type: Array,
      required: true,
    },
    summPrice: {
      type: Number,
      default: 0,
      required: false,
    },
  },
  components: { Product, CartIcon },
  methods: {
    onChangeTab(e) {
      this.tabs.forEach((tab) => {
        if (tab.name === e) {
          tab.condition = true;

          this.activeCategory = e;
        } else {
          tab.condition = false;
        }
      });
      this.$emit("changeActiveTab", e);
    },

    addCart(title, price) {
      this.$emit("addCart", title, price);
    },
    cartOpen() {
      this.$emit("cartOpen");
    },
  },
};
</script>

<style scoped>
.wrapp-cart {
  display: flex;
  justify-content: flex-end;
}
.content__container {
  padding-top: 140px;
  padding-bottom: 100px;
}
.content__title {
  margin-bottom: 50px;
  font-family: Montserrat-Bold, sans-serif;
  font-style: normal;
  font-weight: bold;
  font-size: 48px;
  line-height: 59px;
  text-align: center;
  color: #000000;
}
.tabs-container {
  list-style: none;
  display: flex;
  margin-left: auto;
  margin-right: auto;
  max-width: 830px;
  margin-bottom: 50px;
  justify-content: space-between;
}
.tab {
  width: 145px;
  box-sizing: border-box;
  background: linear-gradient(0deg, #eceef6, #eceef6), #59aaf1;
  border-radius: 45px;
  border: 0;
  outline: 0;
  padding: 17px;
  font-style: normal;
  font-weight: 600;
  font-size: 16px;
  line-height: 140%;
  text-align: center;
  transition: 0.5s;
}
.tab:hover {
  cursor: pointer;
}
.tab.active {
  transition: 0.6s;
  color: #ffffff;
  cursor: pointer;
  background: #59aaf1;
}
.pizza__container {
  display: grid;
  grid-template-columns: repeat(4, 265px);
  grid-column-gap: 20px;
  grid-row-gap: 35px;
  justify-content: center;
  align-items: stretch;
}
.reload {
  width: 60px;
  height: 60px;
  border-radius: 50%;
  box-sizing: border-box;
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 55px auto 0px;
  background: linear-gradient(287.74deg, #f58656 8.52%, #fe5626 92.72%);
  box-shadow: 0px 4px 8px rgba(205, 169, 41, 0.26);
  transition: 0.5s;
}
.reload:hover {
  cursor: pointer;
  transform: rotate(90deg);
  transition: 0.5s;
}

@media screen and (max-width: 1180px) {
  .pizza__container {
    grid-template-columns: repeat(2, 265px);
  }
}
@media screen and (max-width: 880px) {
  .tab {
    width: 90px;
    padding: 10px;
    font-size: 14px;
  }
}
@media screen and (max-width: 650px) {
  .pizza__container {
    grid-template-columns: 265px;
  }
}
@media screen and (max-width: 590px) {
  .tabs-container {
    flex-direction: column;
    align-items: center;
  }
  .tab {
    margin: 10px;
  }
}
</style>
