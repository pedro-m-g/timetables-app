<template>
  <div class="root">
      <button v-on:click="showNewModal = true">Registrar espacio</button>
      
      
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
        <espacios-form @submit="showNewModal = false" />
      </div>
    </div>
  </transition>
      
      
      
      
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
    </div>
  </div>
</template>
<script>
import EspaciosForm from '@/components/Forms/EspaciosForm'
export default {
  components: {
    EspaciosForm
  },
  data () {
      return {
          period: '',
          Groups: [
              {
                id: 1,
                name: 'LD1'
              },
              {
                id: 2,
                name: 'LD2'
              },
             {
                id: 3,
                name: 'Aula Equipada'
              },
              {
                id: 4,
                name: 'D6'
              },
              {
                id: 5,
                name: 'D7'
              }
          ],
          showModal:false,
          showNewModal: false
      }
  },
methods: 
    {
        deletePeriod : function(index){
            //alert(index);
            this.Groups.splice(index-1,1);
        },
        addPeriod : function(){
            this.Groups.push({id:this.Groups.length+1,name:this.period});
            this.period = '';
        }
    
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
</style>
