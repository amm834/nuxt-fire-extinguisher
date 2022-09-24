<template>
  <b-modal id="modal-1" title="Chose date">
    <v-date-picker
      :value="null"
      color="indigo"
      is-dark
      is-range
    />
  </b-modal>
</template>

<script>
export default {
  name: 'RentModal'
}
</script>

<style scoped>

</style>
