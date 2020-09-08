<template>
  <div>
    <nav class="navbar navbar-light bg-white pl-0 pr-0" style="box-shadow: 0 5px 5px -5px #333;">
      <div class="container-fluid">
        <Sidebar/>
        <span class="navbar-brand mb-0 h1">Food items</span>
        <Search/>
      </div>
    </nav>
  </div>
</template>
<script>
import Sidebar from './Partials/Sidebar'
import Search from './Partials/Search'

export default {
  components: {
    Sidebar,
    Search
  }
}
</script>
