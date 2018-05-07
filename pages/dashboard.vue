<template>
  <div>
    <div class="row">
      <div class="col col-2">
        <menu-view />
      </div>
        <div>
            <h3>Hola: Adolfo</h3>
        </div>
      <div class="col col-10">
        <dashboard />
      </div>
    </div>
  </div>
</template>

<script>
import MenuView from '~/components/MenuView.vue'
import Dashboard from '~/components/Dashboard.vue'

export default {
  components: {
    MenuView,
    Dashboard
  },
  layout: 'logged'
}
</script>
