<template>
  <div id="allTheStuff">
    <Navbar />
    <div class="container is-fullhd">
      <Nuxt />
    </div>
  </div>
</template>

<style scoped>
  .container {
    padding-top: 10px;
    margin-left: 5px;
  }
</style>

<script>
import Navbar from '../components/Navbar'

export default {
  components: {
    Navbar
  }
}
</script>
