<template>
  <div class="row">
    <div class="col-12 mb-2">
      <h1 class="display-1 mb-4">Orders</h1>
      <h2>Available Products</h2>
    </div>
    <Product v-for="product in products"
    :name="product.name" :price="product.price"
    :key="product.id"
    v-on:order="addToCart"
    ordered="0"
    />
    <div class="col-12 mt-4 mb-2">
      <h2>Ordered Products</h2>
    </div>
    <Product v-for="product in current_orders" :name="product.name" :price="product.price" :key="product.id" ordered="1" />
  </div>

</template>

<script>
import Product from '@/components/Product'
export default {
  components: {
    Product
  },
  data() {
    return {
      products: [
        { id:1, name: 'Pizza', price: 3.0 },
        { id:2, name: 'Frites', price: 2.0 },
        { id:3, name: 'Hamburger', price: 8.0 },
        { id:4, name: 'CheeseCake', price: 2.5 },
      ],
      current_orders: [

      ]
    }
  },
  methods: {
    addToCart(name, price) {
      this.current_orders.push(
        {
          id: this.current_orders.length,
          name: name,
          price:price
        })
    }
  }
}
</script>

<style scoped>

</style>
