<template>
  <div class="card">
    <div class="card__image-holder">
      <img
        src="./assets/images/image-product-desktop.jpg"
        alt="perfume image"
      />
    </div>
    <div class="card__info">
      <div class="card__info__category">perfume</div>
      <h1 class="card__info__header">gabrielle essence eau de parfum</h1>
      <p class="card__info__body">
        A floral, solar and voluptuous interpretation composed by <br />Olivier
        Polge, Perfumer-Creator for the House of CHANEL.
      </p>
      <div class="card__info__price">
        <div class="card__info__price__current">${{ currentPrice }}</div>
        <div class="card__info__price__past">${{ pastPrice }}</div>
      </div>
      <button class="card__info__button" @click="addCard">
        <img src="./assets/images/icon-cart.svg" alt="cart icon" />
        <span>Add to Cart</span>
      </button>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "App",
  data() {
    return {
      currentPrice: 149.99,
      pastPrice: 169.99,
    };
  },
  methods: {
    addCard() {
      console.log("Product added to cart");
    },
  },
});
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Fraunces:opsz,wght@9..144,700&family=Montserrat:wght@500;700&display=swap");
@import "./assets/scss/_variables.scss";

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: $background-color;
}

#app {
  .card {
    width: 600px;
    height: 450px;
    background-color: $card-color;
    border-radius: 8px;

    display: flex;

    &__image-holder {
      width: 50%;
      img {
        width: 100%;
        height: 100%;
        border-top-left-radius: 8px;
        border-bottom-left-radius: 8px;
      }
    }

    &__info {
      width: 50%;
      padding: 32px;
      color: $body-color;
      font-size: $fs-body;

      &__category {
        text-transform: uppercase;
        letter-spacing: 5px;
        font-family: $ff-body;
        font-size: calc(#{$fs-body} - 2px);
        font-weight: $fw-normal;
      }

      &__header {
        text-transform: capitalize;
        color: $header-color;
        font-family: $ff-header;
        margin-top: 20px;
        font-size: $fs-header;
        line-height: 1;
      }

      &__body {
        margin-top: 23px;
        line-height: 1.65;
        font-size: $fs-body;
        font-weight: $fw-normal;
        font-family: $ff-body;
      }

      &__price {
        display: flex;
        align-items: center;
        margin-top: 25px;
        margin-bottom: 27px;
        font-weight: $fw-bold;

        &__current {
          font-size: $fs-header;
          font-family: $ff-header;
          margin-right: 20px;
          color: $accent-color;
        }

        &__past {
          text-decoration: line-through;
          font-family: $ff-body;
          font-weight: $fw-normal;
          font-size: calc(#{$fs-body} - 1px);
        }
      }

      &__button {
        border: none;
        outline: none;
        width: 100%;
        height: 47px;
        background-color: $accent-color;
        color: $card-color;
        font-weight: $fw-bold;
        font-family: $ff-body;
        font-size: $fs-body;
        border-radius: 8px;

        display: flex;
        align-items: center;
        justify-content: center;

        img {
          margin-right: 10px;
        }

        &:hover {
          background-color: $accent-color-hover;
          cursor: pointer;
          transition: 0.3s;
        }
      }
    }
  }
}
</style>
