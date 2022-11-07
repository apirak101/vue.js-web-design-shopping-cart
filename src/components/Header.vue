<template>
  <header>
    <div class="Header-h">
            <div class="header-left">
                <div class="logo"><a href="#home">Apirak</a></div>
            </div>
            <div class="header-center">
                <ul>
                    <li><a href="#home">HOME</a></li>
                    <li><a href="#recommend">RECOMMEND</a></li>
                    <li><a href="#productlist">PRODUCT LIST</a></li>
                </ul>
            </div>
            <div class="header-right">
                <i class='bx bx-shopping-bag' id="cart-icon" @click="CartIcon"></i>
                <div class="quantity">{{totalQty}}</div>
              </div>  
        </div>
  </header>
</template>

<script>
import { mapGetters } from "vuex";

export default {
  name: "Header",
  computed: {
    ...mapGetters(["cart"]),
    totalQty() {
      return this.cart.reduce((a, b) => a + b.qty, 0);
    },
    
  },
  methods: {
        CartIcon(){
            document.querySelector(".cart").classList.add("active");
        },
      }
};
</script>

<style scoped>

#cart-icon{
  cursor: pointer;
}



.Header-h {
    width: 100%;
    height: 14vh;

    background-color: rgba(255, 255, 255, 0.9);
    box-shadow: 0 1px 10px rgba(0, 0, 0, 0.3);
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    position: fixed;
    top: 0;
    z-index: 400;
}

.header-left {
    flex: 1;

}

.logo a{
    width: 100%;
    height: 100%;
    font-size: 20px;
    font-weight: 600;
    color: #000;
    cursor: pointer;
}

.header-center {
    flex: 1;

}

.header-right {
    flex: 1;
    position: relative;
}

ul {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    list-style: none;
    justify-content: center;
    gap: 40px;

}

li a{
    padding: 10px 5px;
    border-radius: 5px;
    font-weight: 300;
    cursor: pointer;
    color: #000;
    font-weight: 400;
    transition: 250ms;
}

li a:hover {
    box-shadow: 0 1px 10px rgba(0, 0, 0, 0.3);
    text-decoration: none;
}

.bx-shopping-bag {
    font-size: 25px;
    cursor: pointer;
}

.quantity {
    position: absolute;
    top: 50%;
    left: 50%;

    font-size: 12px;
    color: #fff;
    text-align: center;


    width: 20px;
    height: 20px;
    background-color: rgba(0, 125, 19, 0.8);
    border-radius: 50%;
}

@media (max-width: 1230px) {
  ul{
    gap: 10px;
  }
}
@media (max-width: 1050px) {
  ul{
    gap: 10px;
  }
  li{
    font-size: 14px;
  }
}
@media (max-width: 950px) {
  ul{
    gap: 2px;
  }
  li{
    font-size: 10px;
  }
}
@media (max-width: 770px) {
  ul{
    display: none;
  }

}
</style>
