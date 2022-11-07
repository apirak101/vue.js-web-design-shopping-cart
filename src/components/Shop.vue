<template>
  <div class="container reveal" id="productlist">
  <h5>Product List</h5>
  <hr>
  <div class="row">
    <div
      class="card"
      style="width: 15rem;"
      v-for="item in products"
      :key="item.id"
    >
      <img :src="item.imgUrl" class="card-img-top" :alt="item.title" />
      <div class="card-body">
        <p class="card-title" style=" text-align: left; white-space: nowrap; width: 12rem; overflow: hidden; text-overflow: ellipsis;">{{ item.title }}</p>
        <p class="card-text">${{ item.price.toLocaleString() }}  <i class='bx bx-shopping-bag' @click="addItemToCart(item)"></i></p>
       
      </div>
    </div>
  </div>
</div>
</template>

<script>
import { mapActions, mapGetters } from "vuex";

export default {
  name: "Shop",
  
  mounted() {
    this.getProducts();
  },
  computed: {
    ...mapGetters(["products"]),
  },
  methods: {
    ...mapActions(["addItemToCart", "getProducts"]),
  },
};
</script>

<style scoped>

.card {
    margin: 20px;
    text-align: left;
    
}
.card-title{
  font-size: 1.1rem;
  font-weight: 600;
}
.card-text{
  font-weight: 500;
  font-size: 1rem;
}

.card img {
    width: 100%;
    height: 20vh;
    margin-left: auto;
    margin-right: auto;
    
}
.row{
  justify-content: center;
}

.bx-shopping-bag{
   font-size: 1.3rem;
   cursor: pointer;
   float: right;
   color: #fff;
   background-color: rgb(17, 10, 27);
   padding: 7px;
   transition: 300ms;
   border-radius: 3px;
}

.bx-shopping-bag:hover{
    
   color: rgb(0, 0, 0);
   background-color: rgb(249, 244, 255);
   box-shadow: 0 1px 10px rgba(0, 0, 0,0.3);
}
</style>
