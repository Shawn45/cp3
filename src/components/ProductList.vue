<template>
<div class="wrapper">
  <div class="products">
    <div class="product" v-for="product in products" :key="product.id">
      <div class="info">
        <h1>{{product.name}}</h1>

      </div>
      <div class="image">
        <img :src="'/images/products/'+product.image">
      </div>
      <div class="price">
        <h2>{{product.price}}</h2>
        <button class="auto" @click="addToCart(product)">Add to Cart</button>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'ProductList',
  props: {
    products: Array
  },
  methods: {
    addToCart(productIn){
      this.$root.$data.cart.push(productIn);
      this.$root.$data.numberOfItems++;
    }
  }


}


</script>

<style scoped>
.wrapper {
  display: flex;
  margin-bottom: 20px;
  align-items: center;
  justify-content: center;
}

.products {
  margin-top: 20px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}

.product {
  margin: 10px;
  margin-top: 50px;
  width: 200px;
}

.product img {
  border: 2px solid #D3D3D3;
  height: 250px;
  width: 200px;
  object-fit: cover;
}

.product .image {
  display: flex;
  justify-content: center;
  margin-bottom: 5px;
}

.info {
  background: #D3D3D3;
  color: #000;
  padding: 10px 30px;
  height: 60px;
}

.info h1 {
  font-size: 20px;
}

.info h2 {
  font-size: 14px;
}

.info p {
  margin: 0px;
  font-size: 15px;
}


.price {
  display: flex;
  align-items: center;
  justify-content: center;

}

button {
  height: 40px;
  width: 100px;
  background: #f51b00;
  color: white;
  border: none;
}

.auto {
  margin-left: auto;
}
</style>
