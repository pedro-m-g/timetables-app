<template>
  <div class="root">
      <button>Nuevo Horario</button>
      
      <div class="row">
          <div v-for="group in Groups"
            :value="group.id"
            :key="group.id" class="col col-6 square">
          <p>Grupo {{group.name}}</p>
            <p>{{group.description}}</p>
        <div id="options">
             <button class="option">
               <i class="fa fa-eye"></i>
             </button>
             <button class="option">
               <i class="fa fa-pencil"></i>
             </button>
             <button class="option close">
               <i class="fa fa-close"></i>
             </button>
        </div>
      </div>
    </div>
  </div>
</template>
<script>

export default {
  data () {
      return {
          Groups: [
              {
                id: 1,
                name: '6845',
                description: 'Descricion del grupo'
              },
              {
                id: 2,
                name: '4521',
                  description: 'Descricion del grupo'
              },
              {
                id: 3,
                name: '9851',
                description: 'Descricion del grupo'
              },
              {
                id: 4,
                name: '1235',
                description: 'Descricion del grupo'
              }
          ]
      }
  }
}

</script>

<style scoped >
.root {
  padding: 40px;
}
.square{
    width: 250px;
    height: 200px;
    padding: 20px;
    background-color: #eaeaea;
    margin: 25px;
    border-radius: 2px;
    border: solid #c1c1c1 2px;
    position: relative;
}
    
.option {
    display: inline-block;
    background-color: aqua;
    height: 20px;
    width: 35px;
    text-align: center;
    color:black;
}
.close {
  position: absolute;
  right: 10px;
  top: 10px;
}
</style>
