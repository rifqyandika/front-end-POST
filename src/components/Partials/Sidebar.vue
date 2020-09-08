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
        <b-button v-b-modal.modal-1>
          <img src="../../assets/img/menu3.png" class="mb-4" alt />
        </b-button>
      </div>
    </b-sidebar>
    <!-- Modal -->
    <b-modal id="modal-1" title="Add Product" hide-footer>
      <div class="name row mb-2">
        <div class="col-3 pt-1">Name</div>
        <div class="col-9" style="border: none;">
          <input
            type="text"
            class="form-control shadow-sm bg-white rounded"
            aria-label="Sizing example input"
            aria-describedby="inputGroup-sizing-default"
            v-model="name"
          />
        </div>
      </div>
      <div class="name row mb-2">
        <div class="col-3 pt-1">Image</div>
        <div class="col-9" style="border: none;">
          <input
            type="file"
            class="custom-file-input"
            id="inputGroupFile01"
            aria-describedby="inputGroupFileAddon01"
            @change="uploads"
          />
          <label class="custom-file-label" for="inputGroupFile01">Choose file</label>
        </div>
      </div>
      <div class="name row mb-2">
        <div class="col-3 pt-1">Price</div>
        <div class="col-5" style="border: none;">
          <input
            type="text"
            class="form-control shadow-sm bg-white rounded"
            aria-label="Sizing example input"
            aria-describedby="inputGroup-sizing-default"
            v-model="price"
          />
        </div>
      </div>
      <div class="name row mb-2">
        <div class="col-3 pt-1">Category</div>
        <div class="col-5" style="border: none;">
          <div class="dropdown">
            <input
              type="text"
              class="form-control shadow-sm bg-white rounded"
              aria-label="Sizing example input"
              aria-describedby="inputGroup-sizing-default"
              v-model="category"
            />
          </div>
          <b-button class="mt-3" block @click="modalAdd()">Close Me</b-button>
        </div>
      </div>
    </b-modal>
  </div>
</template>
<script>
import axios from 'axios'

export default {
  data () {
    return {
      name: '',
      image: null,
      price: '',
      category: ''
    }
  },
  methods: {
    modalAdd () {
      axios.post('http://localhost:3000/product/add', {
        name: this.name,
        image: this.image,
        price: this.price,
        category: this.category
      }).then(response => {
        console.log(response)
      }).catch(err => {
        console.log(err)
      })
    },
    uploads (event) {
      this.image = event.target.files[0]
    }
  }
}
</script>

<style scoped>
button img {
  width: 24px;
}
b-button {
  background-color: transparent;
}
#sidebar-1 {
  width: 10%;
}
</style>
