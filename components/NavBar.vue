<template>
  <div class="bg-dark text-white">
    <b-nav class="container py-3 d-flex">
      <NuxtLink to="/" class="text-light">Firegii</NuxtLink>
      <div class="ml-auto d-flex flex-row">
        <NuxtLink to="/products" class="text-light">Products</NuxtLink>
        <NuxtLink to="/items" class="text-white mx-4">My Items</NuxtLink>
      </div>
    </b-nav>
  </div>
</template>

<script>
export default {
  name: 'NavBar'
}
</script>

<style scoped>

</style>
