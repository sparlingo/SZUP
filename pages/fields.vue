<template>
  <div id="allTheFields">
    <div v-for="field in fields" :key="field._id" class="fieldMap" style="height: 50vh; width: 100vh;">
      <no-ssr>
        <h3>
          {{ field.title }}
        </h3>
        <l-map :zoom="14" :center="[field.location.lat, field.location.lng]">
          <l-tile-layer url="http://{s}.tile.osm.org/{z}/{x}/{y}.png" />
          <l-marker :lat-lng="[field.location.lat, field.location.lng]" />
        </l-map>
      </no-ssr>
    </div>
  </div>
</template>

<style scoped>
.fieldMap {
  margin-bottom: 20px;
}
</style>

<script>
export default {
  asyncData ({ $sanity }) {
    const query = '{ "fields": *[_type == "playing_field"] }'
    return $sanity.fetch(query)
  }
}
</script>
