<template>
  <div class="col-3 mb-3">
    <div class="card text-white bg-dark">
      <div class="card-header">{{ name }}</div>
      <div class="card-body">
        <p class="card-text">Price: <span class="fs-1">${{ price }}</span></p>
        <hr />
        <button v-if="ordered==0" class="btn btn-info w-100 text-uppercase font-weight-bold"
          @click="$emit('order',name,price)">Buy</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Product",
  props: [
    'name',
    'price',
    'ordered'
  ]
}
</script>

<style scoped>

</style>
