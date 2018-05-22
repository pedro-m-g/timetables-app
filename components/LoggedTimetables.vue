<template>
  <div class="root">
      <!--<tabs>
        <tab
            v-for="semester in timetable.semesters"
            :key="semester.id"
            :name="''" >
          <timetable :timetable="semester.assignments" />
        </tab>
      </tabs>-->
      <div>
      <table>
          <thead>
              <tr>
                  <th>Hora</th>
                  <th>Lunes</th>
                  <th>Martes</th>
                  <th>Miércoles</th>
                  <th>Jueves</th>
                  <th>Viernes</th>
                  <th>Sábado</th>
              </tr>
          </thead>
          <tbody>
              <tr
                v-for="assignment in assignments"
                :key="assignment.id" >
                  <td >{{ assignment.hour }}</td>
                  <td
                    v-for="day in assignment.days"
                    :key="day.id" v-bind:class="{ 'borraclase': isDelete, 'agregaclase': !isDelete }" v-on:click="modifyAssignments(day.id)">
                    {{ day.subject }}
                  </td>
              </tr>
          </tbody>
      </table>
          
        <div id="selectorMaterias">
            <h3>Selecciona una materia para agregar</h3>
            <select v-model="assignmentToAdd">
                <option disabled value="">Seleccionar</option>
                
                <option>Reingeniería de procesos</option>
                <option>Sistemas distribuidos</option>
                <option>PDI</option>
                <option>Compiladores</option>
                <option>MGVDI</option>
            </select>
        </div>
          <h3>Borrar materia</h3><input type="checkbox" v-model="isDelete">

  </div>
      <!--ARREGLAR BUG DEL HOVER, EN LA MITAD DE LA DERECHA NO SE APLICA :( -->
      
  </div>
</template>
<script>
import Tabs from './tabs/Tabs.vue'
import Tab from './tabs/Tab.vue'

import Timetable from './timetables/Timetable.vue'
export default {
  data() {
    return {
            isDelete : false,
            assignmentToAdd : '',
            assignments: [
              {
                hour: '7:00',
                days: [
                  {
                    id: 1,
                    subject: 'Reingenieria de Procesos'
                  },
                  {
                    id: 2,
                    subject: 'MGVDI'
                  },
                  {
                    id: 3,
                    subject: 'PDI'
                  },
                  {
                    id: 4,
                    subject: 'Sistemas Distribuidos'
                  },
                  {
                    id: 5,
                    subject: 'Compiladores'
                  },
                  {
                    id: 6,
                    subject: ''
                  }
                ]
              },
              {
                hour: '8:00',
                days: [
                  {
                    id: 7,
                    subject: 'Reingenieria de Procesos'
                  },
                  {
                    id: 8,
                    subject: 'Sistemas Distribuidos'
                  },
                  {
                    id: 9,
                    subject: 'MGVDI'
                  },
                  {
                    id: 10,
                    subject: 'PDI'
                  },
                  {
                    id: 11,
                    subject: 'Compiladores'
                  },
                  {
                    id: 12,
                    subject: ''
                  }
                ]
              },
                {
                hour: '9:00',
                days: [
                  {
                    id: 13,
                    subject: 'Reingenieria de Procesos'
                  },
                  {
                    id: 14,
                    subject: ''
                  },
                  {
                    id: 15,
                    subject: 'Sistemas Distribuidos'
                  },
                  {
                    id: 16,
                    subject: 'MGVDI'
                  },
                  {
                    id: 17,
                    subject: 'PDI'
                  },
                  {
                    id: 18,
                    subject: 'Compiladores'
                  }
                ]
              },
                {
                hour: '10:00',
                days: [
                  {
                    id: 19,
                    subject: 'MGVDI'
                  },
                  {
                    id: 20,
                    subject: 'PDI'
                  },
                  {
                    id: 21,
                    subject: 'Compiladores'
                  },
                  {
                    id: 22,
                    subject: 'Reingenieria de Procesos'
                  },
                  {
                    id: 23,
                    subject: 'Sistemas Distribuidos'
                  },
                  {
                    id: 24,
                    subject: ''
                  }
                ]
              },
                {
                hour: '11:00',
                days: [
                  {
                    id: 25,
                    subject: 'Compiladores'
                  },
                  {
                    id: 26,
                    subject: 'Sistemas Distribuidos'
                  },
                  {
                    id: 27,
                    subject: ''
                  },
                  {
                    id: 28,
                    subject: 'Reingenieria de Procesos'
                  },
                  {
                    id: 29,
                    subject: 'PDI'
                  },
                  {
                    id: 30,
                    subject: 'MGVDI'
                  }
                ]
              },
                {
                hour: '12:00',
                days: [
                  {
                    id: 31,
                    subject: 'Reingenieria de Procesos'
                  },
                  {
                    id: 32,
                    subject: 'PDI'
                  },
                  {
                    id: 33,
                    subject: ''
                  },
                  {
                    id: 34,
                    subject: 'Compiladores'
                  },
                  {
                    id: 35,
                    subject: ''
                  },
                  {
                    id: 36,
                    subject: 'PDI'
                  }
                ]
              }
            ]
          
        
      
    }
  },
    methods: 
    {
        modifyAssignments : function(index){
            var indice = Math.floor((index-1)/6);
            var indice2 = (index-1)%6;
            if(this.isDelete == true){
                this.assignments[indice].days[indice2].subject = '';
            }
            else{
                this.assignments[indice].days[indice2].subject = this.assignmentToAdd;
                
            }
            
        }
        /*addPeriod : function(){
            this.Groups.push({id:this.Groups.length+1,name:this.period});
            this.period = '';
        }*/
    
    },
  components: {
    Tabs,
    Tab,
    Timetable
  }
}
</script>

<style scoped>
.root {
  padding: 40px;
}
    .borraclase:hover{
        background-color: #e24f4f;
        cursor: pointer;
    }
    .agregaclase:hover{
        background-color: green ;
        cursor: pointer;
    }
</style>