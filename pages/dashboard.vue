<template>
  <div>
    <div class="row">
      <div class="col col-2">
            <MenuView />
    </div>
        
      <div class="col col-10 gutters" v-if="windowActived==0">
        <nuxt-child />
      </div>
        
    </div>
  </div>
</template>

<script>
    
import MenuView from '~/components/MenuView.vue'
import Dashboard from '~/components/Dashboard.vue'
import Materias from '~/components/Materias.vue'
import Academicos from '~/components/Academicos.vue'

export default {
    data(){
      return {
          windowActived : 0
      }  
    },
  components: {
      MenuView,
        Dashboard,
    Materias,
    Academicos
  },
  layout: 'logged'
}
</script>
<style scoped>
  .gutters {
    padding: 0 40px
  }
</style>