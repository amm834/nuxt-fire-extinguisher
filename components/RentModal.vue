<template>
  <div>
    <b-button id="show-btn" class="btn-danger btn-block" @click="showModal">Rent</b-button>

    <b-modal ref="my-modal" hide-footer title="Using Component Methods">
      <div class="d-block text-center">
        <v-date-picker
          :value="null"
          color="indigo"
          is-dark
          is-range
        />
      </div>
      <div class="d-flex justify-content-around mt-3">
        <b-button variant="outline-danger" @click="hideModal">Cancel</b-button>
        <b-button variant="outline-warning" @click="addItem">Order</b-button>
      </div>
    </b-modal>
  </div>
</template>

<script>
import { mapActions } from 'pinia'
import { useProductsStore } from '@/store/products'

export default {
  name: 'RentModal',
  props: ['product'],
  methods: {
    ...mapActions(useProductsStore, ['addToItems']),
    showModal () {
      this.$refs['my-modal'].show()
    },
    hideModal () {
      this.$refs['my-modal'].hide()
    },
    addItem () {
      this.addToItems(this.product)
      this.$refs['my-modal'].toggle('#toggle-btn')
    }
  }
}
</script>
