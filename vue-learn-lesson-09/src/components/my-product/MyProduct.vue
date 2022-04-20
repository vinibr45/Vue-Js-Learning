<template>
    <div class="product">
        <div id="product-image">
          <img v-bind:src="image" />
        </div>

        <div class="product-info"></div>
        <h1>{{ title }}</h1>
        <p v-if="inStock">In Stock</p>
        <p v-else>Out of Stock</p>
        <p> Shipping {{ shipping }} </p>
        <ul id="alinha">
          <li id="alinha-lista" v-for="detail in details" :key="detail">
            {{ detail }}
          </li>
        </ul>
        <div id="quadradinho">
          <div
            v-for="(variant, index) in variants"
            :key="variant.variantId"
            class="color-box"
            :style="{ backgroundColor: variant.variantColor }"
            @mouseover="updateProduct(index)"
          ></div>

          <button
            v-on:click="addToCart"
            :disabled="!inStock"
            :class="{ disabledButton: !inStock }"
          >
            Add to Cart
          </button>

         
        </div>
      </div>
</template>

<script>

export default {
    props: {
        premium: {
            type: Boolean,
            required: true
        }
    },
  methods: {
    addToCart() {
    this.$emit('add-to-cart', this.variants[this.selectedVariant].variantId)
    },
  },
  data() {
    return {
      brand: "Vue Mastery",
      product: "Socks",
      selectedVariant: 0,
      details: ["80% cotton", "20% polyester", "Gender-neutral"],
      variants: [
        {
          variantId: 2234,
          variantColor: "pink",
          variantImage:
            "https://img.clasf.com.br/2020/09/30/meia-patrick-bob-esponja-20200930063020.3608590015.jpg",
          variantQuantity: 10,
        },
        {
          variantId: 2235,
          variantColor: "yellow",
          variantImage:
            "https://www.merchandisingplaza.com.br/403736/2/Meias-Bob-esponja-Meia-Bob-esponja-l.jpg",
          variantQuantity: 10,
        },
      ],
      updateProduct: function (index) {
        this.selectedVariant = index;
        console.log(index);
      },
    };
  },
  computed: {
    title() {
      return this.brand + "" + this.product;
    },
    image() {
      return this.variants[this.selectedVariant].variantImage;
    },
    inStock() {
      return this.variants[this.selectedVariant].variantQuantity;
    },
    shipping () {
        if (this.premium) {
            return "Free"
        }
        return 2.99
    }
  }
}

</script>


<style scoped>


</style>