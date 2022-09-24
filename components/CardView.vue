<template>
  <div class="mt-5 mb-4">
    <h1>{{ largeCards.title }}</h1>
    <p>{{ largeCards.snippet }}</p>
    <b-row class="mt-5" cols="3">
      <b-col
        v-for="card in largeCards.cards"
        :key="card.id"
      >
        <NuxtLink :to="`/products/${card.id}`" class="text-decoration-none">
          <b-card
            :title="card.title"
            img-alt="Image"
            :img-src="require(`~/assets/images/fires/images/${card.image}`)"
            img-top
            tag="article"
            style="max-width: 20rem;"
            class="mb-2"
          >
            <b-card-text>{{ card.snippet }}</b-card-text>
          </b-card>
        </NuxtLink>
      </b-col>
    </b-row>

  </div>
</template>

<script>
export default {
  name: 'CardView',
  props: ['largeCards']
}
</script>

<style scoped>

</style>
