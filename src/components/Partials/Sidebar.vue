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
    <b-modal id="modal-1" title="Add Product" hide-footer>
      <form enctype="multipart/form-data">
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
              @change="uploads($event)"
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
            <select v-model="id_category">
            <option v-for="(item,index) in category" :key="index" :value="item.id_category">{{item.category}}</option>
            </select>
          </div>
        </div>
        <b-button class="mt-3" block @click="modalAdd()">Add Product</b-button>
      </form>
    </b-modal>
  </div>
</template>
<script>
import axios from 'axios'

export default {
  data () {
    return {
      name: null,
      price: null,
      image: null,
      id_category: null,
      category: null
    }
  },
  methods: {
    modalAdd () {
      const fd = new FormData()
      fd.append('name', this.name)
      fd.append('price', this.price)
      fd.append('image', this.image)
      fd.append('category', this.id_category)
      axios.post('http://localhost:3002/product/add', fd).then((response) => {
        alert('Product add Success')
      }).catch(err => {
        console.log(err)
      })
    },
    uploads (event) {
      this.image = event.target.files[0]
    },
    getCategory () {
      axios
        .get('http://localhost:3002/category')
        .then((response) => {
          this.category = response.data.data
        })
        .catch((err) => {
          console.log(err)
        })
    }
  },
  mounted () {
    this.getCategory()
  }
}
</script>

<style scoped>
button img {
  width: 24px;
}
</style>
