<template>

<body>
 <div id="nav-bar"></div>
<div id="app">
    <div class="product">
        <div id="product-image">
          <img v-bind:src="image" >
        </div>


   <div class="product-info"> </div>
   <h1> {{ product }}</h1>
   <p v-if="inStock"> In Stock </p>
   <p v-else> Out of Stock </p>
<ul id="alinha">
<li id="alinha2" v-for="detail in details" :key="detail"> {{ detail }}</li>
</ul>

<div v-for="variant in variants" :key="variant">
  <p @mouseover="updateProduct(variant.variantImage)"> {{ variant.variantColor }} </p>


  <button v-on:click="cart += 1"> Add to Cart </button>

  <div class="cart">
    <p>Cart({{cart}})</p>
  </div>
</div>
    </div>
  </div>
</body>
</template>
<script>

export default {
  data() {
    return{
      product: 'Socks',
      image: 'https://img.clasf.com.br/2020/09/30/meia-patrick-bob-esponja-20200930063020.3608590015.jpg',
      inStock:true,
      details:["80% cotton", "20% polyester", "Gender-neutral"],
    variants: [
{
  variantId: 2234,
  variantColor: 'Meia do Patriki',
  variantImage: 'https://img.clasf.com.br/2020/09/30/meia-patrick-bob-esponja-20200930063020.3608590015.jpg'
},
{
  variantId: 2235,
  variantColor: 'Meia do Esponjo BOBO',
  variantImage: 'https://www.merchandisingplaza.com.br/403736/2/Meias-Bob-esponja-Meia-Bob-esponja-l.jpg'
 },
    ],
        cart:0, 
        updateProduct: function (variantImage) {
        this.image = variantImage
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
#product-image {
width: 80px;
height: 120px;
}

#alinha{
padding-left: 900px;

}

#alinha2{
padding-right: 870px;

}

</style>
