<template>
  <div>
    <Navbar />
    <div class="container is-fullhd">
      <Nuxt />
    </div>
  </div>
</template>

<script>
import Navbar from '../components/Navbar'

export default {
  components: {
    Navbar
  }
}
</script>
