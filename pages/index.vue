<template>
  <div class="hero">
    <h1 class="title">
      Shenzhen Ultimate Frisbee
    </h1>
  </div>
</template>

<script>
export default {
  asyncData ({ $sanity }) {
    const query = '{ "fields": *[_type == "playing_field"] }'
    return $sanity.fetch(query)
  }
}
</script>

<style>

</style>
