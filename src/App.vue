<template>
  <div id="app">
    <Header />
    <Home />
    <Recommend />
    <Shop />
    <Cart />

  </div>
</template>

<script>
import Header from "./components/Header";
import Shop from "./components/Shop";
import Cart from "./components/Cart";
import Home from "./components/Home.vue";
import Recommend from "./components/Recommend.vue";



export default {
  name: "App",
  components: {
    Shop,
    Header,
    Cart,
    Home,
    Recommend,
  },
  data() {
    function reveal() {
      var reveals = document.querySelectorAll(".reveal");

      for (var i = 0; i < reveals.length; i++) {
        var windowHeight = window.innerHeight;
        var elementTop = reveals[i].getBoundingClientRect().top;
        var elementVisible = 150;

        if (elementTop < windowHeight - elementVisible) {
          reveals[i].classList.add("active");
        } else {
          reveals[i].classList.remove("active");
        }
      }
    }

    window.addEventListener("scroll", reveal);
  },
  



};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap');
*{
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
#app {
  font-family: 'Poppins', sans-serif;
  color: rgb(17, 17, 17);
}

html {
  scroll-behavior: smooth;
}


::-webkit-scrollbar{
  width: 15px;
}

::-webkit-scrollbar-track{
  background: #dddd;
}

::-webkit-scrollbar-thumb{
  background: #505050;
}
.reveal {
  position: relative;
  transform: translateY(150px);
  opacity: 0;
  transition: 1s all ease;
}

.reveal.active {
  transform: translateY(0);
  opacity: 1;
}
</style>
