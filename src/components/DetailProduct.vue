<template>
  <div class="row no-gutters bg-light">
    <div class="col-lg-12 col-md-12 col-sm-12 col-xs-6 mx-auto">
      <div class="row p-1 mx-auto">
        <div class="col-6 col-lg-8 col-md-4 col-sm-6 col-xs-6 p-2 mx-auto">
          <div class="card mb-3 shadow" style="max-width: 80rem;">
            <div class="card-header bg-primary text-white">Edit Product</div>
            <div class="card-body text-primary">
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
                    <select v-model="id_category" title="category">
                      <option
                        v-for="(item,index) in category"
                        :key="index"
                        :value="item.id_category"
                      >{{item.category}}</option>
                    </select>
                  </div>
                </div>
                <b-button class="mt-3" block @click="getUpdate()">Edit Product</b-button>
              </form>
            </div>
          </div>
        </div>
      </div>
    </div>
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
    getData () {
      axios
        .get('http://localhost:3002/product/' + this.$route.params.id)
        .then((response) => {
          this.name = response.data.data[0].name
          this.price = response.data.data[0].price
          this.image = response.data.data[0].image
          this.id_category = response.data.data[0].id_category
        })
        .catch((err) => {
          console.log(err)
        })
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
    },
    getUpdate () {
      const fd = new FormData()
      fd.append('name', this.name)
      fd.append('price', this.price)
      fd.append('image', this.image)
      fd.append('category', this.id_category)
      console.log(this.id_category)
      axios.put(`http://localhost:3002/product/edit/${this.$route.params.id}`, fd)
        .then((response) => {
          alert('update success')
          console.log(response)
        }).catch(err => {
          console.log(err)
        })
    },
    uploads (event) {
      this.image = event.target.files[0]
    }
  },
  mounted () {
    this.getData()
    this.getCategory()
  }
}
</script>
