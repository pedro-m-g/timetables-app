<template>
  <div>
    <div class="row">
      <div class="col col-2">
        <SearchTimetables />
      </div>
      <div class="col col-10">
        10 cols
      </div>
    </div>
  </div>
</template>

<script>
import SearchTimetables from '~/components/SearchTimetables.vue'

export default {
  components: {
    SearchTimetables
  },
  layout: 'guest'
}
</script>
