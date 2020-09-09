<template>
  <div class="row no-gutters bg-light">
    <div class="col-lg-12 col-md-12 col-sm-12 col-xs-6 mx-auto">
      <div class="row no-gutters pt-3">
        <div class="container-fluid">
          <div class="col-12 text-right">
            <button class="btn btn-primary mr-1" @click="sortDesc()">Terbaru</button>
            <button class="btn btn-info mr-1" @click="sortPrice()">Termurah</button>
          </div>
        </div>
      </div>
      <div class="row p-1 mx-auto">
        <div
          class="col-6 col-lg-3 col-md-4 col-sm-6 col-xs-6 p-2"
          v-for="(item, index) in product"
          :key="index"
        >
          <Card :product="item" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Card from '../components/Partials/Card'
import axios from 'axios'
import { EventBus } from '@/event-bus.js'

export default {
  data () {
    return {
      product: [],
      search: ''
    }
  },
  components: {
    Card
  },
  methods: {
    getProduct () {
      axios
        .get('http://localhost:3002/product')
        .then((response) => {
          this.product = response.data.data
        })
        .catch((err) => {
          console.log(err)
        })
    },
    getSearch (value) {
      axios('http://localhost:3002/product?search=' + value)
        .then((response) => {
          this.product = response.data.data
        })
        .catch((err) => {
          console.log(err)
        })
    },
    sortPrice () {
      axios.get('http://localhost:3002/product?sortBy=price&type=asc')
        .then((response) => {
          this.product = response.data.data
        }).catch(err => {
          console.log(err)
        })
    },
    sortDesc () {
      axios.get('http://localhost:3002/product?sortBy=id_product&type=desc')
        .then((response) => {
          this.product = response.data.data
        }).catch(err => {
          console.log(err)
        })
    }
  },
  mounted () {
    this.getProduct()
  },
  created () {
    EventBus.$on('search-v', (value) => {
      this.getSearch(value)
    })
  }
}
</script>
