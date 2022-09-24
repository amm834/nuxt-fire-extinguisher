<template>
  <div>
    <nav-bar></nav-bar>
    <b-container>
      <card-view
        v-for="(largeCards,idx) in largeCards.slice(0,1)"
        :key="idx"
        :largeCards="largeCards"
      />
      <small-card-view
        v-for="smallCard in smallCards"
        :key="smallCard.id"
        :smallCards="smallCard"
      />
    </b-container>
  </div>
</template>

<script>
import { largeCardSections, smallCardSections } from 'assets/data'

export default {
  name: 'products-index',
  data: () => ({
    smallCards: smallCardSections,
    largeCards: largeCardSections
  })
}
</script>
