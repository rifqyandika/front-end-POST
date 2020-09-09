<template>
  <div>
    <button class="btn" v-b-toggle.sidebar-1>
      <img src="../../assets/img/toggler.png" alt />
    </button>
    <b-sidebar
      id="sidebar-1"
      title="Menu"
      shadow
      class="bg-danger"
      width="110px"
      bg-variant="white"
    >
      <div class="px-4 py-3">
        <router-link to="/">
          <img src="../../assets/img/menu1.png" alt class="mb-4" />
        </router-link>
        <br />
        <router-link to="/dashboard">
          <img src="../../assets/img/menu2.png" class="mb-4" alt />
        </router-link>
        <br />
        <b-button v-b-modal.modal-1 variant="link">
          <img src="../../assets/img/menu3.png" class="mb-4" alt />
        </b-button>
      </div>
    </b-sidebar>
    <!-- Modal -->
    <ModalAdd/>
  </div>
</template>
<script>
import ModalAdd from './ModalAdd'

export default {
  components: {
    ModalAdd
  }
}
</script>

<style scoped>
button img {
  width: 24px;
}

</style>
