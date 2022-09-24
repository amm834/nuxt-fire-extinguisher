<template>
  <div class="container my-5" v-if="product">
    <b-row cols="2">
      <b-col>
        <img class="w-100 h-100" :src="require(`~/assets/images/fires/images/${product.image}`)" alt="image">
      </b-col>
      <b-col>
        <h1>{{product.title}}</h1>
        <p>{{product.description}}</p>
        <b-button variant="danger">Rent</b-button>
      </b-col>
    </b-row>
  </div>
  <div v-else>
    No product found
  </div>
</template>

<script>

import { mapGetters } from 'pinia'
import { useProductsStore } from '@/store/products'

export default {
  name: '_id',
  computed: {
    ...mapGetters(useProductsStore, ['getProductById']),
    product () {
      return this.getProductById(this.$route.params.id)
    }
  }
}
</script>

<style scoped>

</style>
