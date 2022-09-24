<template>
  <div v-if="product" class="container my-5">
    <b-row cols="2">
      <b-col>
        <img class="w-100 h-100" :src="require(`~/assets/images/fires/images/${product.image}`)" alt="image">
      </b-col>
      <b-col>
        <h1>{{ product.title }}</h1>
        <p>{{ product.description }}</p>
        <b-button variant="danger" v-b-modal.modal-1>Rent</b-button>
        <RentModal/>
      </b-col>
    </b-row>
    <div>
      <div v-if="!$fetchState.pending">
        <div class="mt-3" v-for="user in users.results" :key="user.login.uuid">
          <div class="mb-2 card py-3 px-3">
            {{ user.name.first }}
          </div>
        </div>
      </div>
      <div v-else>
        Loading
      </div>
    </div>
  </div>
  <div v-else>
    <PageNotFound/>
  </div>
</template>

<script>

import { mapGetters } from 'pinia'
import { useProductsStore } from '@/store/products'

export default {
  name: '_id',
  data: () => ({
    users: []
  }),
  async fetch () {
    this.users = await fetch(
      'https://randomuser.me/api/?results=5'
    ).then(res => res.json())
  },
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
