<template>
  <div>
    <LoggedNavbar />
    <nuxt/>
  </div>
</template>
<script>
import LoggedNavbar from '~/components/LoggedNavbar.vue'
export default {
  components: {
      LoggedNavbar
  }
}
</script>
