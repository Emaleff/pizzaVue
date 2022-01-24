<template>
  <div id="app">
    <CartBlock
      v-if="cardVisible"
      :isCartVisible="isCartVisible"
      :selectedProducts="selectedProducts"
      :summPrice="summPrice"
      @cartClose="cartClose"
      @deleteItem="deleteItem"
      @minusCount="minusCount"
      @plusCount="plusCount"
    />
    <Main />
    <Products
      :summPrice="summPrice"
      :tabs="tabs"
      :activeProducts="activeProducts"
      @changeActiveTab="onChangeTab"
      @addCart="addCart"
      @cartOpen="cartOpen"
    />
    <Swiper />
    <Form />
    <Footer />
  </div>
</template>

<script>
import Main from "./components/Main.vue";
import Products from "./components/Products.vue";
import Swiper from "./components/Swiper.vue";
import Form from "./components/Form.vue";
import Footer from "./components/Footer.vue";
import CartBlock from "./components/CartBlock.vue";

export default {
  name: "App",
  data: () => ({
    isCartVisible: false,
    cardVisible: false,
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
    products: [
      {
        type: "Pizza",
        title: "Белуччи",
        description:
          "Томатный соус, колбаски пепперони, бекон, свежие шампиньоны, орегано, маслины и сыр Моцарелла",
        img: "pizza1",
        hit: false,
        price: 435,
        count: 0,
      },
      {
        type: "Pizza",
        title: "Пепперони",
        description:
          "Томатный соус, итальянские колбаски пепперони и сыр Моцарелла",
        img: "pizza2",
        hit: true,
        price: 405,
        count: 0,
      },
      {
        type: "Pizza",
        title: "Гавайская",
        description:
          "Томатный соус, цыпленок, сыр Моцарелла, ананасы, соус Терияки",
        img: "pizza3",
        hit: true,
        price: 395,
        count: 0,
      },
      {
        type: "Pizza",
        title: "Ветчина и грибы",
        description: "Чесночный соус, ветчина, шампиньоны и сыр Моцарелла",
        img: "pizza4",
        hit: false,
        price: 415,
        count: 0,
      },
      {
        type: "Pizza",
        title: "Синица",
        description:
          "Сырный соус, острые колбаски пепперони, шампиньоны, жареный лук, томаты, сыр Моцарелла ",
        img: "pizza5",
        hit: false,
        price: 425,
        count: 0,
      },
      {
        type: "Pizza",
        title: "Сырная",
        description:
          "Томатный соус, увеличенная порция сыра Моцарелла и орегано",
        img: "pizza6",
        hit: false,
        price: 245,
        count: 0,
      },
      {
        type: "Pizza",
        title: "Мачете",
        description:
          "Томатный соус, Соус BBQ, колбаса пепперони, лук красный, шампиньоны свежие, халапеньо, фрикадельки и сыр Моцарелла",
        img: "pizza7",
        hit: false,
        price: 445,
        count: 0,
      },
      {
        type: "Pizza",
        title: "Тамбовский мясник",
        description:
          "Соус томатный, колбаса чоризо, перец болгарский, сыр моцарелла, окорок тамбовский, красный лук, маслины и соус барбекю",
        img: "pizza8",
        hit: true,
        price: 455,
        count: 0,
      },
      {
        type: "Sushi",
        title: "Санлайт сэт",
        description:
          "48шт. Филадельфия классик 8 шт, Лава 8 шт, Темпура микс 8 шт, Яки тори гриль 8 шт, Сенсей 8 шт, Сяке маки 8 шт.",
        img: "Sushi1",
        hit: true,
        price: 945,
        count: 0,
      },
      {
        type: "Sushi",
        title: "Гурман Сэт",
        description:
          "16 шт. Филадельфия 4 шт, Унаги филадельфия 4 шт, Калифорния 4 шт, Лава 4 шт",
        img: "Sushi2",
        hit: false,
        price: 925,
        count: 0,
      },
      {
        type: "Sushi",
        title: "Биг Компани Сэт",
        description:
          "32 шт. Лава гриль 4 шт, Запеченный с цыпленком 8 шт, Запеченный с лососем 8 шт, Моцарелли 4 шт, Запеченный с креветкой 4 шт, Запеченная гейша 4 шт",
        img: "Sushi3",
        hit: true,
        price: 1015,
        count: 0,
      },
      {
        type: "Sushi",
        title: "Бинго Сэт",
        description:
          "20 шт. Сяки чиз 4 шт, Унаги филадельфия лайт 4 шт, Капа маки 4 шт, Хоккайдо 4 шт, Острый лосось 4 шт",
        img: "Sushi4",
        hit: false,
        price: 855,
        count: 0,
      },
      {
        type: "Salad",
        title: "Цезарь с курицей",
        description:
          "салат айсберг, соус цезарь, сыр пармезан, томаты, копченая курица, сухарики",
        img: "Salad1",
        hit: true,
        price: 155,
        count: 0,
      },
      {
        type: "Salad",
        title: "Поке с морепродуктами",
        description:
          "Отварной рис, салат «Айсберг», лосось, мясо краба, салат «Чука»",
        img: "Salad2",
        hit: false,
        price: 125,
        count: 0,
      },
      {
        type: "Salad",
        title: "Чука",
        description:
          "Отварной рис, огурец свежий, ореховый соус, водоросли хияши вакаме",
        img: "Salad3",
        hit: false,
        price: 135,
        count: 0,
      },
      {
        type: "Salad",
        title: "ВИТАМИННЫЙ",
        description:
          "Капуста белокочанная, уксус, соль, оливковое масло, перец черный.",
        img: "Salad4",
        hit: false,
        price: 75,
        count: 0,
      },
      {
        type: "Dessert",
        title: "Пончик клубничный с начинкой",
        description: "Просроченный Пончик клубничный с начинкой",
        img: "Dessert1",
        hit: false,
        price: 65,
        count: 0,
      },
      {
        type: "Dessert",
        title: "Пончик карамельный с начинкой",
        description: "Не свежий Пончик карамельный с начинкой",
        img: "Dessert2",
        hit: false,
        price: 75,
        count: 0,
      },
      {
        type: "Dessert",
        title: "Пончик шоколадный с кокосовой стружкой",
        description: "Пончик шоколадный с кокосовой стружкой",
        img: "Dessert3",
        hit: false,
        price: 85,
        count: 0,
      },
      {
        type: "Dessert",
        title: "Чизкейк Орео",
        description: "Чизкейк Орео",
        img: "Dessert4",
        hit: false,
        price: 95,
        count: 0,
      },
      {
        type: "Drinks",
        title: "Dr.Pepper Classic",
        description: "Dr.Pepper Classic",
        img: "Drinks1",
        hit: false,
        price: 105,
        count: 0,
      },
      {
        type: "Drinks",
        title: "Coca-Cola",
        description: "Coca-Cola",
        img: "Drinks2",
        hit: false,
        price: 150,
        count: 0,
      },
      {
        type: "Drinks",
        title: "Sprite",
        description: "Sprite",
        img: "Drinks3",
        hit: false,
        price: 150,
        count: 0,
      },
      {
        type: "Drinks",
        title: "Fanta",
        description: "Fanta",
        img: "Drinks4",
        hit: false,
        price: 150,
        count: 0,
      },
    ],
    // selectedProducts: [],
    activeCategory: "Pizza",
  }),
  computed: {
    activeProducts() {
      return this.products.filter(
        (product) => product.type === this.activeCategory
      );
    },
    selectedProducts() {
      return this.products.filter((product) => product.count >= 1);
    },
    summPrice() {
      let summ = 0;
      this.products.forEach((product) => {
        summ = summ + product.price * product.count;
      });
      return summ;
    },
  },
  methods: {
    minusCount(title) {
      this.products.forEach((item) => {
        if (item.title === title) {
          item.count = item.count - 1;
        }
      });
    },
    plusCount(title) {
      this.products.forEach((item) => {
        if (item.title === title) {
          item.count = item.count + 1;
        }
      });
    },
    deleteItem(title) {
      this.products.forEach((item) => {
        if (item.title === title) {
          item.count = 0;
        }
      });
    },
    cartOpen() {
      this.isCartVisible = true;
      this.cardVisible = true;
    },
    addCart(title, price) {
      console.log(title, price);
      this.products.forEach((item) => {
        if (item.title === title) {
          item.count = item.count + 1;
        }
      });
    },
    cartClose() {
      this.isCartVisible = false;
      setTimeout(() => {
        this.cardVisible = false;
      }, 300);
    },
    onChangeTab(e) {
      this.tabs.forEach((tab) => {
        if (tab.name === e) {
          tab.condition = true;

          this.activeCategory = e;
        } else {
          tab.condition = false;
        }
      });
    },
  },
  components: {
    Main,
    Products,
    Swiper,
    Form,
    Footer,
    CartBlock,
  },
};
</script>

<style>
@font-face {
  font-family: Montserrat-Regular;
  src: url(./assets/fonts/Montserrat-Regular.ttf);
}
@font-face {
  font-family: Montserrat-Bold;
  src: url(./assets/fonts/Montserrat-Bold.ttf);
}
* {
  margin: 0;
  font-family: Montserrat-Regular, sans-serif;
  padding: 0;
}
#app {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
.container {
  max-width: 1160px;
  margin: 0 auto;
}
@media screen and (max-width: 1180px) {
  .container {
    width: 95%;
  }
}
</style>
