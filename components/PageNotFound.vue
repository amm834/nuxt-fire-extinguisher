<template>
  <div>
    <NuxtLink to="/" class="px-5 m-5">Back to Home</NuxtLink>
    <b-row cols="2">
      <b-col class="d-flex align-items-center justify-content-center">
        page not found
      </b-col>
      <b-col class="d-flex align-items-center justify-content-center">
        <img class="w-50 h-50" :src="require(`~/assets/images/fires/images/fe25.jpg`)" alt="not found">
      </b-col>
    </b-row>
  </div>
</template>

<script>
export default {
  name: 'PageNotFound'
}
</script>

<style scoped>

</style>
