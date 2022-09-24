<template>
  <div>
    <PageNotFound v-if="error.statusCode === 404"/>
    >
  </div>
</template>

<script>
export default {
  name: 'errors-no',
  props: ['error']
}
</script>

<style scoped>

</style>
