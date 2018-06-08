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
      <transition name="modal" v-if="showModal">
    <div class="modal-mask">
      <div class="modal-wrapper">
        <div class="modal-container">

          <h3>Modificar Entrada</h3>
          <select id="seleccionarDocente" v-model="docenteSeleccionado">
              <option selected disabled>Docente</option>
              <option>Victoria Meza</option>
              <option>José Lozano</option>
              <option>Angel Fraga</option>
              <option>Everardo Gutierrez</option>
        </select><br><br>
            <select id="seleccionarAula" v-model="aulaSeleccionada">
              <option selected disabled>Aula</option>
              <option>D6</option>
              <option>D7</option>
              <option>LD1</option>
              <option>LD2</option>
        </select>
            <div class="modal-footer">
            <slot name="footer">
              <button class="modal-default-button" v-on:click="modificarEntidades()">
                OK
              </button>
            </slot>
          </div>
        </div>
      </div>
    </div>
  </transition>
      <div>
          <button v-on:click="inicializar()">Nuevo Horario</button>
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
                    :key="day.id" class="item" v-on:click="modifyAssignments(day.id)" style="text-align: center;">
                    {{ day.subject }} <br>
                      <p class="entidadAsignada" v-if="day.subject.length > 1" v-on:click="showModal = true; idModified = day.id">{{day.profesorAsignado}}</p>
                      <p class="entidadAsignada" v-if="day.subject.length > 1" v-on:click="showModal = true; idModified = day.id">{{day.edificioAsignado}}</p>
                  </td>
                  <!-- v-bind:class="{ 'borraclase': isDelete, 'agregaclase': !isDelete }" -->
              </tr>
          </tbody>
      </table>
          
        <div id="selectorMaterias">
            <h3>Modificar Horario</h3>
            <select v-model="assignmentToAdd">
                <option disabled value="">Seleccionar opción</option>
                <option id="borrarAsignatura">Quitar asignatura</option>
                <!--<option id="modificarAsignatura">Modificar Asignatura</option> -->
                <option>Reingeniería de procesos</option>
                <option>Sistemas distribuidos</option>
                <option>PDI</option>
                <option>Compiladores</option>
                <option>MGVDI</option>
                
            </select>
        </div>
          <!--<h3>Borrar materia</h3><input type="checkbox" v-model="isDelete">-->

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
            isModify: false,
            showModal: false,
            assignmentToAdd : '',
            aulaSeleccionada : '',
            docenteSeleccionado : '',
            idModified : 0,
            //profesorAsignado: 'Vacante',
            //edificioAsignado: 'D1',
            assignments: [
              {
                hour: '7:00',
                days: [
                  {
                    id: 1,
                    subject: 'Reing. Proc',
                      profesorAsignado: 'Vacante',
                      edificioAsignado: 'D1'
                  },
                  {
                    id: 2,
                    subject: 'MGVDI',
                      profesorAsignado: 'Vacante',
                      edificioAsignado: 'D1'
                  },
                  {
                    id: 3,
                    subject: 'PDI',
                      profesorAsignado: 'Vacante',
                      edificioAsignado: 'D1'
                  },
                  {
                    id: 4,
                    subject: 'Sistemas Distribuidos',
                      profesorAsignado: 'Vacante',
                      edificioAsignado: 'D1'
                  },
                  {
                    id: 5,
                    subject: 'Compiladores',
                      profesorAsignado: 'Vacante',
                      edificioAsignado: 'D1'
                  },
                  {
                    id: 6,
                    subject: '',
                      profesorAsignado: 'Vacante',
                      edificioAsignado: 'D1'
                  }
                ]
              },
              {
                hour: '8:00',
                days: [
                  {
                    id: 7,
                    subject: 'Reing. Proc',
                      profesorAsignado: 'Vacante',
                      edificioAsignado: 'D1'
                  },
                  {
                    id: 8,
                    subject: 'Sistemas Distribuidos',
                      profesorAsignado: 'Vacante',
                      edificioAsignado: 'D1'
                  },
                  {
                    id: 9,
                    subject: 'MGVDI',
                      profesorAsignado: 'Vacante',
                      edificioAsignado: 'D1'
                  },
                  {
                    id: 10,
                    subject: 'PDI',
                      profesorAsignado: 'Vacante',
                      edificioAsignado: 'D1'
                  },
                  {
                    id: 11,
                    subject: 'Compiladores',
                      profesorAsignado: 'Vacante',
                      edificioAsignado: 'D1'
                  },
                  {
                    id: 12,
                    subject: '',
                      profesorAsignado: 'Vacante',
                      edificioAsignado: 'D1'
                  }
                ]
              },
                {
                hour: '9:00',
                days: [
                  {
                    id: 13,
                    subject: 'Reing. Proc',
                      profesorAsignado: 'Vacante',
                      edificioAsignado: 'D1'
                  },
                  {
                    id: 14,
                    subject: '',
                      profesorAsignado: 'Vacante',
                      edificioAsignado: 'D1'
                  },
                  {
                    id: 15,
                    subject: 'Sistemas Distribuidos',
                      profesorAsignado: 'Vacante',
                      edificioAsignado: 'D1'
                  },
                  {
                    id: 16,
                    subject: 'MGVDI',
                      profesorAsignado: 'Vacante',
                      edificioAsignado: 'D1'
                  },
                  {
                    id: 17,
                    subject: 'PDI',
                      profesorAsignado: 'Vacante',
                      edificioAsignado: 'D1'
                  },
                  {
                    id: 18,
                    subject: 'Compiladores',
                      profesorAsignado: 'Vacante',
                      edificioAsignado: 'D1'
                  }
                ]
              },
                {
                hour: '10:00',
                days: [
                  {
                    id: 19,
                    subject: 'MGVDI',
                      profesorAsignado: 'Vacante',
                      edificioAsignado: 'D1'
                  },
                  {
                    id: 20,
                    subject: 'PDI',
                      profesorAsignado: 'Vacante',
                      edificioAsignado: 'D1'
                  },
                  {
                    id: 21,
                    subject: 'Compiladores',
                      profesorAsignado: 'Vacante',
                      edificioAsignado: 'D1'
                  },
                  {
                    id: 22,
                    subject: 'Reing. Proc',
                      profesorAsignado: 'Vacante',
                      edificioAsignado: 'D1'
                  },
                  {
                    id: 23,
                    subject: 'Sistemas Distribuidos',
                      profesorAsignado: 'Vacante',
                      edificioAsignado: 'D1'
                  },
                  {
                    id: 24,
                    subject: '',
                      profesorAsignado: 'Vacante',
                      edificioAsignado: 'D1'
                  }
                ]
              },
                {
                hour: '11:00',
                days: [
                  {
                    id: 25,
                    subject: 'Compiladores',
                      profesorAsignado: 'Vacante',
                      edificioAsignado: 'D1'
                  },
                  {
                    id: 26,
                    subject: 'Sistemas Distribuidos',
                      profesorAsignado: 'Vacante',
                      edificioAsignado: 'D1'
                  },
                  {
                    id: 27,
                    subject: '',
                      profesorAsignado: 'Vacante',
                      edificioAsignado: 'D1'
                  },
                  {
                    id: 28,
                    subject: 'Reing. Proc',
                      profesorAsignado: 'Vacante',
                      edificioAsignado: 'D1'
                  },
                  {
                    id: 29,
                    subject: 'PDI',
                      profesorAsignado: 'Vacante',
                      edificioAsignado: 'D1'
                  },
                  {
                    id: 30,
                    subject: 'MGVDI',
                      profesorAsignado: 'Vacante',
                      edificioAsignado: 'D1'
                  }
                ]
              },
                {
                hour: '12:00',
                days: [
                  {
                    id: 31,
                    subject: 'Reing. Proc',
                      profesorAsignado: 'Vacante',
                      edificioAsignado: 'D1'
                  },
                  {
                    id: 32,
                    subject: 'PDI',
                      profesorAsignado: 'Vacante',
                      edificioAsignado: 'D1'
                  },
                  {
                    id: 33,
                    subject: '',
                      profesorAsignado: 'Vacante',
                      edificioAsignado: 'D1'
                  },
                  {
                    id: 34,
                    subject: 'Compiladores',
                      profesorAsignado: 'Vacante',
                      edificioAsignado: 'D1'
                  },
                  {
                    id: 35,
                    subject: '',
                      profesorAsignado: 'Vacante',
                      edificioAsignado: 'D1'
                  },
                  {
                    id: 36,
                    subject: 'PDI',
                      profesorAsignado: 'Vacante',
                      edificioAsignado: 'D1'
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
            //alert(this.assignmentToAdd);
            if(this.assignmentToAdd == "Quitar asignatura"){
                this.isDelete = true;
                //this.isModify = false;
            }
            else{
                 this.isDelete = false;
            }
            /*if(this.assignmentToAdd == "Modificar Asignatura"){
                this.isDelete = false;
                this.isModify = true;
            }*/
            /*else{
                this.isModify = false;
            }*/
            if(this.isDelete == true ){
                this.assignments[indice].days[indice2].subject = '';
            }
            else{
                if(this.assignmentToAdd != ''){
                    this.assignments[indice].days[indice2].subject = this.assignmentToAdd;
                }
               
                
            }
            
        },
        modificarEntidades: function(){
            //this.showModal = true;
            //alert(document.getElementById("seleccionarDocente").selectedIndex);
            //this.idModified = index;
            //alert("hola");
            var index = this.idModified;
            var indice = Math.floor((index-1)/6);
            var indice2 = (index-1)%6;
            this.assignments[indice].days[indice2].profesorAsignado = this.docenteSeleccionado;
            this.assignments[indice].days[indice2].edificioAsignado = this.aulaSeleccionada;
            this.showModal = false;
        },
        inicializar(){
            for(var i=0;i<this.assignments.length;i++){
                for(let dia of this.assignments[i].days){
                    dia.profesorAsignado = 'Vacante';
                    dia.subject = '';
                    dia.edificioAsignado = 'D1';
                }
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
    .item:hover{
        background-color: #eaeaea;
        cursor: pointer;
    }
    .borraclase:hover{
        background-color: #e24f4f;
        cursor: pointer;
    }
    .agregaclase:hover{
        background-color: green ;
        cursor: pointer;
    }
    #borrarAsignatura{
        color: #e24f4f;
        font-weight: bold;
    }
    #modificarAsignatura{
        color: green;
        font-weight: bold;
    }
    .entidadAsignada{
        text-align: center;
        font-size: 10px;
    }
    
    
    
    
    .modal-mask {
  position: fixed;
  z-index: 9998;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, .5);
  display: table;
  transition: opacity .3s ease;
}

.modal-wrapper {
  display: table-cell;
  vertical-align: middle;
}

.modal-container {
  width: 300px;
height: 300px;
  margin: 0px auto;
  padding: 20px 30px;
  background-color: #fff;
  border-radius: 2px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, .33);
  transition: all .3s ease;
  font-family: Helvetica, Arial, sans-serif;
  
}

.modal-header h3 {
  margin-top: 0;
  color: #42b983;
}

.modal-body {
  margin: 20px 0;
}

.modal-default-button {
  float: right;
  margin-top: 50px;
}
   

/*
 * The following styles are auto-applied to elements with
 * transition="modal" when their visibility is toggled
 * by Vue.js.
 *
 * You can easily play with the modal transition by editing
 * these styles.
 */

.modal-enter {
  opacity: 0;
}

.modal-leave-active {
  opacity: 0;
}

.modal-enter .modal-container,
.modal-leave-active .modal-container {
  -webkit-transform: scale(1.1);
  transform: scale(1.1);
}
</style>