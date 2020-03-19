<template>
<div>
  <div class="pure-menu pure-menu-horizontal">
    <ul class="pure-menu-list">
      <li class="pure-menu-item"><a @click="select('fruit')" href="#" class="pure-menu-link">fruit</a></li>
      <li class="pure-menu-item"><a @click="select('snack')" href="#" class="pure-menu-link">snack</a></li>
      <li class="pure-menu-item"><a @click="select('nuddle')" href="#" class="pure-menu-link">nuddle</a></li>
      <li class="pure-menu-item"><a @click="select('sea food')" href="#" class="pure-menu-link">sea food</a></li>
    </ul>
  </div>
  <ProductList :products="products" />
</div>
</template>


<script>
import ProductList from "../components/ProductList.vue"
export default {
  name: 'Browse',
  components: {
    ProductList
  },
  data() {
    return {
      country: '',
    }
  },
  computed: {
    products() {
      return this.$root.$data.products.filter(product => product.country === this.country);
    }
  },
  methods: {
    select(country) {
      this.country = country;
    }
  }
}
</script>
