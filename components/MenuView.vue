<template>
    
  <div>
      
      <div class="sidebar">
      
      <ul id="list">
          <li
            v-for="type in Types"
            :key="type.id"
            class="element">
                <nuxt-link :to="type.url">
                    {{ type.name }}
                </nuxt-link>
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
                name: 'Escritorio',
                url: '/dashboard/'
              },
              {
                id: 2,
                name: 'Asignaturas',
                url: '/dashboard/materias'
              },
              {
                id: 3,
                name: 'Espacios',
                url: '/dashboard/espacios'
              },
              {
                id: 4,
                name: 'Académicos',
                url: '/dashboard/academicos'
              }
          ]
      }
  }
}
</script>

<style>
    #username-field{
        text-align: center;
    }
    .sidebar{
        width: 350px;
    }
    #list > li{
        list-style: none;
    }
    .element {
        margin-top: 25px;
        height: 50px;
        text-align: center;
        cursor: pointer;
        padding: 15px;
    }
    
    .element:hover{
        background-color: #5eab5e;
        color: white;
    }

    .element a {
        text-decoration: none;
        color: black;
        width: 100%;
    }
</style>
