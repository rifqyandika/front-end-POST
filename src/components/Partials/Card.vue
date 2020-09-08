<template>
  <div class="card">
    <img :src="`http://localhost:3002/${product.image}`" alt class="img-fluid" />
    <div class="card-title mb-0 p-2">
      <h5 class="mb-0">{{product.name}}</h5>
      <h3>Rp. {{product.price}}</h3>
      <div class="action text-center">
        <button class="btn btn-primary mr-1">Add Cart</button>
        <button class="btn btn-danger">Detail</button>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: ['product']
}
</script>
