<template>
  <div>
    <div class="row">
      <div class="col col-2">
        <menu-view />
      </div>
        <div>
            <h3>Hola: Adolfo</h3>
            <div class="button-group">
                <button v-on:click="windowActived = 0">Periodo</button>
                <button v-on:click="windowActived = 1">Asignaturas</button>
                <button v-on:click="windowActived = 2">Académicos</button>
            </div>
        </div>
      <div class="col col-10" v-if="windowActived==0">
        <dashboard />
      </div>
        <div class="col col-10" v-if="windowActived==1">
        <materias />
      </div>
        <div class="col col-10" v-if="windowActived==2">
        <academicos />
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
