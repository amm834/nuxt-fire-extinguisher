<template>
  <b-container>
    <hero-page></hero-page>
    <card-view
      v-for="(largeCards,idx) in largeCards"
      :key="idx"
      :largeCards="largeCards"
    />
  </b-container>
</template>

<script>
import HeroPage from '~/components/Hero'
import { largeCardSections } from '~/assets/data'

export default {
  name: 'IndexPage',
  components: { HeroPage },
  data: () => {
    return {
      largeCards: largeCardSections
    }
  }
}
</script>
