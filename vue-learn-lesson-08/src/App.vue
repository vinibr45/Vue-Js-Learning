<template>
  <body>
    <div id="nav-bar"></div>
    <div id="app">
      <my-product :premium="premium"></my-product>
    </div>
  </body>
</template>
<script>
import MyProduct from "./components/my-product/MyProduct.vue";

export default {
  components: {
  MyProduct,
  },
  data () {
    return{

      premium: false
    }

  }

};
</script>


<style>
#nav-bar {
  margin-top: -40px;
  margin-left: -20px;
  margin-right: -20px;
  padding: 70px;
  background-image: linear-gradient(120deg, #8fd3f4 0%, #84fab0 100%);
}
.product-info {
  font-family: "Gill Sans", "Gill Sans MT", Calibri, "Trebuchet MS", sans-serif;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

#alinha {
  margin-left: 820px;
  font-style: italic;
  font-family: "Trebuchet MS", "Lucida Sans Unicode", "Lucida Grande",
    "Lucida Sans", Arial, sans-serif;
}

#alinha-lista {
  margin-right: 900px;
}

#product-image {
  width: 80px;
  height: 120px;
}

.cart {
  margin-right: 600px;
  float: right;
  border: 1px solid #d8d8d8;
  padding: 5px 20px;
  margin-bottom: 15px;
}

button {
  margin-bottom: 5px;
  border: none;
  background-color: #1e95ea;
  color: white;
  height: 40px;
  width: 100px;
}

.disabledButton {
  background-color: #d8d8d8;
}

#cartText {
  padding-right: 400px;
}

#quadradinho {
  margin-left: 1000px;
}

.color-box {
  width: 40px;
  height: 40px;
  margin-top: 5px;
}
</style>
