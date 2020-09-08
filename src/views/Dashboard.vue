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
          <p>menu</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Navbar from '../components/Navbar'

export default {
  components: {
    Navbar
  }
}
</script>
