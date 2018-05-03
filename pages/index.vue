<template>
  <div>
    <div class="row">
      <div class="col col-2">
        <search-timetables />
      </div>
      <div class="col col-10">
        <guest-timetables />
      </div>
    </div>
  </div>
</template>

<script>
import SearchTimetables from '~/components/SearchTimetables.vue'
import GuestTimetables from '~/components/GuestTimetables.vue'

export default {
  components: {
    SearchTimetables,
    GuestTimetables
  },
  layout: 'guest'
}
</script>
