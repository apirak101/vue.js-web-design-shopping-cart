<template>
  <div class="cart">
    <div v-if="!cart.length" class="alert alert-secondary" role="alert">There are no products in the cart !</div>
    <div
      v-if="orderPlaced"
      @click="() => this.orderPlaced=false"
      class="alert alert-success alert-dismissible fade show"
      role="alert"
    >
     Your order has been sent successfully.
      <button
        type="button"
        class="close"
        data-dismiss="alert"
        aria-label="Close"
      >
        <span aria-hidden="true">&times;</span>
      </button>
    </div>
    <ul class="list-group">
      <li class="list-group-item" v-for="item in cart" :key="item.id">
        <button
          @click="removeItemFromCart(item.id)"
          type="button"
          class="close"
          data-dismiss="modal"
          aria-label="Close"
        >
          <span aria-hidden="true">&times;</span>
        </button>
        <div class="media">
          <img width="80px" :src="item.imgUrl" class="mr-3" alt="item.title" />
          <div class="media-body">
            <p class="mt-0">{{ item.title }}</p>
            <button class="qty-button btn btn-sm btn-dark" @click="reduceQty(item.id)">-</button>
            x {{ item.qty }}
            <button
              class="qty-button btn btn-sm btn-dark"
              @click="addQty(item.id)"
            >+</button>
          </div>
        </div>
      </li>
    </ul>
    <button
      v-if="cart.length"
      @click="placeOrder"
      class="checkout-button btn btn-lg btn-block btn-danger"
      :disabled="isProcessing"
    >
      <div v-if="isProcessing" class="spinner-border" role="status">
        <span class="sr-only">Loading...</span>
      </div>
      <span v-else>Buy Now ${{ totalPrice.toLocaleString() }}</span>
    </button>
    <i class="bx bx-x" id="close-cart" @click="closeCart"></i>
  </div>
</template>

<script>
import { mapGetters, mapActions } from "vuex";

export default {
  name: "Cart",
  data() {
    return {
      isProcessing: false,
      orderPlaced: false
    };
  },
  computed: {
    ...mapGetters(["cart"]),
    totalPrice() {
      return this.cart.reduce((a, b) => a + b.qty * b.price, 0);
    }
  },
  methods: {
    ...mapActions(["removeItemFromCart", "addQty", "reduceQty", "emptyCart"]),
    placeOrder() {
      this.isProcessing = true;
      setTimeout(() => {
        this.isProcessing = false;
        this.orderPlaced = true;
        this.emptyCart();
      }, 1000);
    },
    closeCart(){
            document.querySelector(".cart").classList.remove("active");
    },
  }
};
</script>

<style scoped>

.cart {
    position: fixed;
    top: 0;
    right: -100%;
    width: 360px;
    min-height: 100vh;
    padding: 20px;
    background: rgb(236, 236, 236);
    box-shadow: -2px 0 4px hsl(0 4% 15% / 10%);
    transition: 0.3s;
    z-index: 500;
}

.cart.active{
    right: 0;
}

#close-cart{
    position: absolute;
    top: 1rem;
    right: 1.5rem;
    font-size: 2rem;
    cursor: pointer;
}
.media {
  width: 90%;
  text-align: left;
}

.qty-button {
  border-radius: 50%;
  height: 30px;
  width: 30px;
}

.checkout-button {
  margin-top: 20px;
}
.alert-secondary,.list-group{
  margin-top: 2rem;
}

.btn-danger{
    border: none;
    transition: 300ms;
}

.btn-danger:hover{
    border: none;
    background: #fff;
    box-shadow: 0 1px 10px rgba(0, 0, 0,0.3);
    color: black;
}

.btn-dark{
    border: none;
    transition: 300ms;
}

.btn-dark:hover{
    border: none;
    background: #fff;
    box-shadow: 0 1px 10px rgba(0, 0, 0,0.3);
    color: black;
}
</style>