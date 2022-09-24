<template>
  <div class="my-4">
    <h1> {{ smallCards.title }}</h1>
    <b-row cols="4">
      <b-col
        v-for="card in smallCards.cards"
        :key="card.id"
        class="mb-3"
      >
        <img
          class="w-100 h-100"
          :src="require(`~/assets/images/fires/images/${card.image}`)"
          alt="fe"
        />
      </b-col>
    </b-row>
  </div>
</template>

<script>
export default {
  name: 'SmallCardView',
  props: ['smallCards']
}
</script>

<style scoped>

</style>
