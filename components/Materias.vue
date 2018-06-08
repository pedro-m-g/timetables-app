<template>
  <div class="root">
      <button v-on:click="showNewModal = true">Registrar Asignatura</button>
      
      
      <transition name="modal" v-if="showModal">
    <div class="modal-mask">
      <div class="modal-wrapper">
        <div class="modal-container">

          <h3>En construcción</h3>

          <div class="modal-footer">
            <slot name="footer">
              <button class="modal-default-button" @click="showModal = false">
                OK
              </button>
            </slot>
          </div>
        </div>
      </div>
    </div>
  </transition>
      
      <!-- nuevo horario-->
      <transition name="modal" v-if="showNewModal">
    <div class="modal-mask">
      <div class="modal-wrapper">
        <materias-form @submit="showNewModal = false" />
      </div>
    </div>
  </transition>
      
      
      
     <!-- 
      <div class="row">
          <div v-for="group in Groups"
            :value="group.id"
            :key="group.id" class="col col-6 square">
          <p>{{group.name}}</p>
        <div id="options">
             <button class="option" @click="showModal = true">
               <i class="fa fa-eye"></i>
             </button>
             <button class="option">
               <i class="fa fa-pencil"></i>
             </button>
             <button class="option close" v-on:click="deletePeriod(group.id)">
               <i class="fa fa-close"></i>
             </button>
        </div>
              
      </div>
    </div> -->
      
      <div class="row">
          <div class="col col-6" id="optativas">
          <h3>Asignaturas Obligatorias</h3>
              <button class="accordion">Etapa Básica</button>
                <div v-for="materia in basicasObligatorias"
            :value="materia.id"
            :key="materia.id" class="panel">
                    <p alt="Eliminar materia" class="materia" v-on:click="deleteMateria(materia.id,basicasObligatorias)">{{materia.name}}</p></div>

                <button class="accordion" v-on:click="displayAcordion">Etapa Disciplinaria</button>
                <div v-for="materia in diciplinariasObligatorias"
            :value="materia.id"
            :key="materia.id" class="panel">
                    <p alt="Eliminar materia" class="materia">{{materia.name}}</p></div>

                <button class="accordion" v-on:click="displayAcordion">Etapa Terminal</button>
                <div v-for="materia in terminalesObligatorias"
            :value="materia.id"
            :key="materia.id" class="panel">
                    <p alt="Eliminar materia" class="materia">{{materia.name}}</p></div>
        </div>
          
          
      <div class="col col-6" id="optativas">
          <h3>Asignaturas Optativas</h3>
              <button class="accordion">Etapa Básica</button>
                <div v-for="materia in basicasOptativas"
            :value="materia.id"
            :key="materia.id" class="panel">
                    <p alt="Eliminar materia" class="materia">{{materia.name}}</p></div>

                <button class="accordion" v-on:click="displayAcordion">Etapa Disciplinaria</button>
                <div v-for="materia in diciplinariasOptativas"
            :value="materia.id"
            :key="materia.id" class="panel">
                    <p alt="Eliminar materia" class="materia">{{materia.name}}</p></div>

                <button class="accordion" v-on:click="displayAcordion">Etapa Terminal</button>
                <div v-for="materia in terminalesOptativas"
            :value="materia.id"
            :key="materia.id" class="panel">
                    <p alt="Eliminar materia" class="materia">{{materia.name}}</p></div>
        </div>
    </div>
      
  </div>
</template>
<script>
import MateriasForm from '@/components/Forms/MateriasForm'
export default {
  components: {
    MateriasForm
  },
  data () {
      return {
          period: '',
          isActivedAc1 : false,
          basicasObligatorias: [
              {
                id: 1,
                name: 'Comunicación Oral y escrita'
              },
              {
                id: 2,
                name: 'Diseño de Algoritmos'
              },
             {
                id: 3,
                name: 'Cálculo Diferencial'
              },
              {
                id: 4,
                name: 'Geometría Vectorial'
              },
              {
                id: 5,
                name: 'Algebra Superior'
              },
              {
                id: 6,
                name: 'Historia e Impacto de la Ciencia	'
              },
              {
                id: 7,
                name: 'Formación de Valores'
              },
              {
                id: 5,
                name: 'Algebra Lineal'
              },
              {
                id: 5,
                name: 'Mecánica'
              },
              {
                id: 5,
                name: 'Introducción a la Programación'
              },
              {
                id: 5,
                name: 'Cálculo Integral'
              },
              {
                id: 5,
                name: 'Métodos Experimentales'
              },
              {
                id: 5,
                name: 'Estructura de datos y algoritmos'
              },
              {
                id: 5,
                name: 'Cálculo Vectorial'
              },
              {
                id: 5,
                name: 'Probabilidad'
              },
              {
                id: 5,
                name: 'Matemáticas discretas'
              },
              {
                id: 5,
                name: 'Álgebra Lineal II'
              },
              {
                id: 5,
                name: 'Estructura socio-económica de México'
              },
          ],
          diciplinariasObligatorias: [
              {
                id: 1,
                name: 'Análisis de Algoritmos'
              },
              {
                id: 2,
                name: 'Metodología de la programación'
              },
             {
                id: 3,
                name: 'Teoría de Autómatas'
              },
              {
                id: 4,
                name: 'Ingeniería de software'
              },
              {
                id: 5,
                name: 'Compiladores'
              },
              {
                id: 5,
                name: 'Redes de datos'
              },
              {
                id: 5,
                name: 'Teoría de grupos'
              },
              {
                id: 5,
                name: 'Geometría'
              },
              {
                id: 5,
                name: 'Cálculo avanzado'
              },
              {
                id: 5,
                name: 'Análisis matemático'
              },
              {
                id: 5,
                name: 'Métodos numéricos'
              },
              {
                id: 5,
                name: 'Ecuaciones diferenciales ordinarias'
              },
              {
                id: 5,
                name: 'Métodos Experimentales'
              },
              {
                id: 5,
                name: 'Electricidad y magnetismo'
              },
              {
                id: 5,
                name: 'Circuitos eléctricos'
              },
              {
                id: 5,
                name: 'Tensores de relatividad especial'
              },
              {
                id: 5,
                name: 'Física térmica'
              },
              {
                id: 5,
                name: 'Estructura de la materia'
              },
              {
                id: 5,
                name: 'Métodos matemáticos de la física'
              },
          ],
          terminalesObligatorias: [
              {
                id: 1,
                name: 'Sistemas distribuidos'
              },
              {
                id: 2,
                name: 'Reingenieria de procesos'
              },
             {
                id: 3,
                name: 'Simulación'
              },
              {
                id: 4,
                name: 'Aspectos Legales,Sociales y éticos de la comptuación'
              },
              {
                id: 5,
                name: 'Didáctica'
              },
              {
                id: 5,
                name: 'Modelación Lineal'
              },
              {
                id: 5,
                name: 'Habilidades del pensamiento y didáctica de las matemáticas	'
              },
              {
                id: 5,
                name: 'Teoría electromagnética'
              },
              {
                id: 5,
                name: 'Mecánica Estadística'
              },
              {
                id: 5,
                name: 'Física computacional'
              }
          ],
          basicasOptativas: [
              {
                id: 1,
                name: 'Introduccion a las ciencias computacionales'
              }
              
          ],
          showModal:false,
          showNewModal: false
      }
  },
methods: 
    {
        deleteMateria : function(index,arreglo){
            //alert(index);
            this.arreglo.splice(index-1,1);
        },
        addPeriod : function(){
            this.Groups.push({id:this.Groups.length+1,name:this.period});
            this.period = '';
        },
        
    
    }
}

</script>

<style scoped >
.root {
  padding: 40px;
}
    .fa-close:hover{
        color: #ba181d;
    }
    .fa-pencil:hover{
        color:#c1c1c1;
    }
    .fa-eye:hover{
        color:#c1c1c1;
    }
.square{
    width: 250px;
    height: 120px;
    padding: 20px;
    background-color: #eaeaea;
    margin: 25px;
    border-radius: 2px;
    border: solid #c1c1c1 2px;
    position: relative;
}
input{
        padding: 10px 10px 10px 10px;
    }
.option {
    
    background: none;
    
    text-align: center;
    color:black;
}
.close {
  position: absolute;
  right: 10px;
  top: 10px;
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
  width: 80%;
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
  margin-top: 120px;
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
    #obligatorias{
        margin-left: 250px;
    }
    
    .accordion {
    background-color: #eee;
    color: #444;
    cursor: pointer;
    padding: 18px;
    width: 100%;
    text-align: left;
    border: none;
    outline: none;
    transition: 0.4s;
        
}

/* Add a background color to the button if it is clicked on (add the .active class with JS), and when you move the mouse over it (hover) */
.active, .accordion:hover {
    background-color: #ccc;
}
    
    .materia:hover{
        text-decoration: underline;
        cursor: pointer;
        color: red;
    }
/* Style the accordion panel. Note: hidden by default */
.panel {
    padding: 0 18px;
    background-color: white;
    display: block;
    overflow: hidden;
}

</style>
