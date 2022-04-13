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
<li id="alinha-lista" v-for="detail in details" :key="detail"> {{ detail }}</li>
</ul>
<div id="quadradinho">
<div v-for="variant in variants" 
:key="variant.variantId"
class="color-box"
:style="{backgroundColor: variant.variantColor}"
@mouseover="updateProduct(variant.variantImage)">
</div>

   <button v-on:click="addToCart" 
   :disabled="!inStock"
   class="{disabledButton: !inStock}"> Add to Cart </button>

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
 
  methods:{
  addToCart(){
this.cart += 1
  }
    
  },
  data() {
    return{
      product: 'Socks',
      image: 'https://img.clasf.com.br/2020/09/30/meia-patrick-bob-esponja-20200930063020.3608590015.jpg',
      inStock:false,
      details:["80% cotton", "20% polyester", "Gender-neutral"],
    variants: [
{
  variantId: 2234,
  variantColor: 'pink',
  variantImage: 'https://img.clasf.com.br/2020/09/30/meia-patrick-bob-esponja-20200930063020.3608590015.jpg'
},
{
  variantId: 2235,
  variantColor: 'yellow',
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
#nav-bar{
margin-top: -40px;
margin-left: -20px;
margin-right: -20px;
padding: 70px;
background-image: linear-gradient(120deg, #8fd3f4 0%,#84fab0 100%);
  }
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

#alinha{
  margin-left: 820px ;
  font-style: italic;
  font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
}

#alinha-lista{
  margin-right: 900px

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

#cartText{
padding-right: 400px;
}

#quadradinho{
  margin-left: 1000px;
}

.color-box {
  width: 40px;
  height: 40px;
  margin-top: 5px;
}
</style>
