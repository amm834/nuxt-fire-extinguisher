<template>
  <div>
    <div class="container my-5">
      <div
        class="card px-3 py-2 mb-3"
        v-for="rental in myRentals"
        :key="rental.id"
      >
        <div class="card-img">
          <img :src="require(`~/assets/images/fires/images/${rental.image}`)" alt="image">
        </div>
        <div class="card-content">
          <h1>{{ rental.title }}</h1>
          <p>{{ rental.snippet }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { mapState } from 'pinia'
import { useProductsStore } from '@/store/products'

export default {
  name: 'ItemPage',
  computed: {
    ...mapState(useProductsStore, ['myRentals'])
  }
}
</script>
