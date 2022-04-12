<template>

<body>
 <div id="nav-bar"></div>
<div id="app">
    <div class="product">
        <div id="product-image">
          <img v-bind:src="produto.image" >
        </div>


   <div class="product-info"> </div>
   <h1> {{ produto.product }}</h1>
   <p v-if="produto.inStock"> In Stock </p>
   <p v-else> Out of Stock </p>
<ul id="alinha">
<li id="alinha2" v-for="detail in produto.details" :key="detail"> {{ detail }}</li>
</ul>

<div v-for="variant in variants" :key="variant">
  <p> {{ variant.variantColor }} </p>
</div>
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
      inStock:true,
      details:["80% cotton", "20% polyester", "Gender-neutral"]
      
      },
    variants: [
{
  variantId: 2234,
  variantColor: "rosa",
},
{
  variantId: 2235,
  variantColor: "azul",
}
]
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
