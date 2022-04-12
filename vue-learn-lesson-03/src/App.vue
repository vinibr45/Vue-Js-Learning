<template>

<body>
 <div id="nav-bar"></div>
<div id="app">
    <div class="product">
        <div class="product-image">
          <img v-bind:src="produto.image" >
        </div>


   <div class="product-info"> </div>
   <h1> {{ produto.product }}</h1>
   <p v-if="produto.inventory > 10"> In Stock </p>
   <p v-else-if="produto.inventory <= 10 && produto.inventory> 0"> Almost Sold out </p>
   <p v-else> Out of Stock </p>
    </div>
  </div>
</body>
</template>
<script>
export default {
  data() {
    return{
      produto: {
      product: 'Socks',
      image: 'https://img.clasf.com.br/2020/09/30/meia-patrick-bob-esponja-20200930063020.3608590015.jpg',
      inventory:0
      }
    }
  }
}
</script>


<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
#nav-bar{
margin-top: -40px;
margin-left: -20px;
margin-right: -20px;
padding: 70px;
background-image: linear-gradient(120deg, #8fd3f4 0%,#84fab0 100%);
  }
.product-image {

width: 80px;
height: 120px;



}
</style>
