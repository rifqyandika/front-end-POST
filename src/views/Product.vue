<template>
  <div>
    <Navbar />
    <div class="container-fluid">
      <div class="row p-3">
        <div class="col-md-2">
          <b-list-group>
            <b-list-group-item to="/">Main</b-list-group-item>
            <b-list-group-item to="/product">Product</b-list-group-item>
            <b-list-group-item to="/dashboard">Category</b-list-group-item>
          </b-list-group>
        </div>
        <div class="col-md-10">
          <Product/>
          <button>tes</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Navbar from '../components/Navbar'
import Product from '../components/Dashboard.vue/Product'

export default {
  components: {
    Navbar,
    Product
  }
}
</script>
