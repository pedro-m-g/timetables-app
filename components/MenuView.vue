<template>
    
  <div>
      <div class="username">
          <h3>Hola: Adolfo</h3>
        </div>
      <div class="sidebar">
      
      <ul id="list">
          <li
            v-for="type in Types"
            :value="type.id"
            :key="type.id" class="element">
            {{ type.name }}
          </li>
    </ul>
 </div>
    </div>
</template>
<script>
    
export default {
  data () {
      return {
          Types: [
              {
                id: 1,
                name: 'Escritorio'  
              },
              {
                id: 2,
                name: 'Materias'
              },
              {
                id: 3,
                name: 'Espacios'  
              },
              {
                id: 4,
                name: 'Académicos'  
              }
          ]
      }
  }
}
</script>

<style>
    .sidebar{
        width: 350px;
    }
    .flex-column{
        
    }
    #list > li{
        list-style: none;
    }
    .element{
        
        margin-top: 25px;
        height: 50px;
        text-align: center;
        cursor: pointer;
        padding-top: 15px; 
        
    }
    .element:hover{
        background-color: #5eab5e;
        color: white;
    }
</style>
