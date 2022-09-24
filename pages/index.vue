<template>
  <main>
    <b-container>
      <hero-page></hero-page>
      <card-view
        v-for="(largeCards,idx) in largeCards"
        :key="idx"
        :largeCards="largeCards"
      />
      <small-card-view
        v-for="smallCard in smallCards"
        :key="smallCard.id"
        :smallCards="smallCard"
      />
    </b-container>
  </main>
</template>

<script>
import HeroPage from '~/components/Hero'
import { largeCardSections, smallCardSections } from '~/assets/data'

export default {
  name: 'IndexPage',
  components: { HeroPage },
  data: () => {
    return {
      largeCards: largeCardSections,
      smallCards: smallCardSections
    }
  }
}
</script>
