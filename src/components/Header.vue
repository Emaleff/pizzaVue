<template>
  <div class="container header__container">
    <div class="header__links">
      <a href="#" class="header__link">Payment</a>
      <a href="#" class="header__link">About us</a>
      <a href="#" class="header__link">Contacts</a>
    </div>
    <img src="../assets/logo.png" class="header__logo" alt="" />

    <div class="header__info">
      <div class="header__time">Daily 11am - 9pm</div>
      <a href="tel:0 800 33 08 98" class="header__phone">
        <div class="header__phone-img">
          <svg
            width="14"
            height="14"
            viewBox="0 0 14 14"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M12.8766 9.1894C12.0195 9.1894 11.1779 9.05534 10.3804 8.79178C9.98956 8.65849 9.50915 8.78077 9.27064 9.02573L7.69648 10.2141C5.87091 9.23956 4.74639 8.11541 3.7852 6.30354L4.93856 4.77039C5.23821 4.47114 5.34569 4.03401 5.21692 3.62385C4.95223 2.82213 4.81777 1.98093 4.81777 1.12343C4.81781 0.503964 4.31385 0 3.69442 0H1.12339C0.503962 0 0 0.503964 0 1.12339C0 8.22365 5.77637 14 12.8766 14C13.496 14 14 13.496 14 12.8766V10.3127C14 9.69336 13.496 9.1894 12.8766 9.1894Z"
            />
          </svg>
        </div>
        <span class="header__phone-number"> 0 800 33 08 98 </span>
      </a>
    </div>

    <!-- <span class="header__burger burger" id="burger"> &#9776 </span> -->
  </div>
</template>

<script>
export default {
  name: "Header",
};
</script>

<style scoped>
.header__container {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  padding-top: 25px;
}
.header__links {
  width: 300px;
  display: flex;
  justify-content: space-between;
}
.header__link {
  font-style: normal;
  font-weight: normal;
  font-size: 16px;
  line-height: 20px;
  text-decoration: none;
  color: #000000;
  z-index: 1;
}
.header__link:hover {
  cursor: pointer;
  opacity: 0.8;
}
.header__logo {
  justify-self: center;
  z-index: 1;
  margin-bottom: -13px;
}
.header__info {
  width: 340px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-left: 40px;
}
.header__time {
  font-style: normal;
  font-weight: normal;
  font-size: 16px;
  line-height: 20px;
  color: #000000;
}

.header__phone {
  width: 187px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  text-decoration: none;
}
.header__phone-img {
  width: 33px;
  height: 33px;
  border-radius: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
  background: linear-gradient(287.74deg, #f58656 8.52%, #fe5626 92.72%);
  box-shadow: 0px 4px 8px rgba(205, 169, 41, 0.26);
  transition: 2s;
}
.header__phone-img svg {
  fill: white;
}
.header__phone-img:hover svg {
  fill: yellow;
}
.header__phone-img:hover {
  background: green;
}
.header__phone-number {
  font-family: Montserrat-Bold, sans-serif;
  font-style: normal;
  font-weight: bold;
  font-size: 18px;
  line-height: 22px;
  color: #000000;
  text-decoration: none;
}
@media screen and (max-width: 880px) {
  .header__links,
  .header__info {
    display: none;
  }
}
</style>
