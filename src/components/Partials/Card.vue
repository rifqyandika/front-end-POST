<template>
  <div class="card shadow">
    <img :src="`http://localhost:3002/${product.image}`" alt class="img-fluid" />
    <div class="card-title mb-0 p-2">
      <h5 class="mb-0">{{product.name}}</h5>
      <h3>Rp. {{product.price}}</h3>
      <div class="action text-center">
        <router-link @click="getUpdate()" :to="`/detail/`+ product.id_product" class="btn btn-primary mr-1">Edit</router-link>
        <button @click="getUpdate()" class="btn btn-info mr-1"><b-icon icon="cart-plus"></b-icon></button>
        <button @click="getid()" class="btn btn-danger">Delete</button>
      </div>
    </div>
  </div>
</template>
<script>
import axios from 'axios'

export default {
  props: ['product'],
  methods: {
    getid () {
      axios.delete('http://localhost:3002/product/delete/' + this.product.id_product)
        .then((response) => {
          alert('Delete success')
          location.reload()
          console.log(response)
        }).catch((err) => {
          console.log(err)
        })
    },
    getUpdate () {
      alert(
        this.product.name
      )
    }
  }
}
</script>
