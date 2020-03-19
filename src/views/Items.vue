

<template>
<div class="wrapper">
  <div class="comment" v-if="$root.$data.cart.length === 0">
  No Items!
  </div>
  <div class="products" v-else>
    <div class="product" v-for="item in $root.$data.cart" :key="item.id">
      <div class="info">
        <h1>{{item.name}}</h1>
      </div>
      <div class="image">
        <img :src="'/images/products/'+item.image">
      </div>
      <div class="price">
        <h2>{{item.price}}</h2>
      </div>
      <div class="buttonBox">
        <button class="auto" @click="removeFromCart(item)">Remove from Cart</button>
      </div>
    </div>
  </div>
</div>
</template>


<script>
export default {
  name: 'Items',
  props: {
    products: Array
  },
  methods: {
    removeFromCart(itemIn){
      var i = this.$root.$data.cart.indexOf(itemIn);
      this.$root.$data.cart.splice(i,1);
      this.$root.$data.numberOfItems--;
    }
  }


}

</script>

<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}

.comment {
  font-size: 20px;
  padding: 40px;
  border: 2px solid #D3D3D3;
  background: #f51b00;

}

.products {
  margin-top: 20px;
  margin-bottom: 20px;
}

.product {
  margin: 10px;
  margin-top: 30x;
  width: 700px;
  display: flex;
  justify-content: space-around;
}

.product img {
  border: 2px solid #D3D3D3;
  height: 60px;
  width: 48px;
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
  width: 250px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.info h1 {
  font-size: 20px;
}

.info h2 {
  font-size: 14px;
}

.info p {
  margin: 0px;
  font-size: 10px;
}


.price {
  display: flex;
  align-items: center;
  justify-content: center;
}
.buttonBox {
  padding-left: 20px;
}

button {
  padding: 20px;
  height: 60px;
  background: #f51b00;
  color: white;
  font-weight: strong;
  border: none;
}

.auto {
  margin-left: auto;
}
</style>
