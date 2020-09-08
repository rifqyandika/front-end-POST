<template>
  <div>
    <form class="form-inline my-2 my-lg-0">
      <input class="form-control" v-model="search" type="search" placeholder="Search" aria-label="Search" @keyup="getSearch"/>
    </form>
  </div>
</template>
<script>
import { EventBus } from '@/event-bus.js'

export default {
  data () {
    return {
      search: ''
    }
  },
  methods: {
    getSearch () {
      EventBus.$emit('search-v', this.search)
    }
  }
}
</script>
