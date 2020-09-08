<template>
  <div class="home">
    <div class="row no-gutters">
      <div class="col-lg-9 col-md-12 col-sm-12">
        <Navbar/>
        <Content/>
      </div>
      <div class="col-lg-3">
        <Cart/>
      </div>
    </div>
  </div>
</template>

<script>
import Navbar from '../components/Navbar'
import Cart from '../components/Cart'
import Content from '../components/Content'
export default {
  components: {
    Navbar,
    Cart,
    Content
  }
}
</script>
