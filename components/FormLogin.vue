<template>
    <div class="search-timetables">
      <fieldset>
          <form action="/dashboard">
            <label>
                <h1>Nombre de Usuario</h1>
            </label>
            <input type="text" name="username">

            <label>
                <h1>Contraseña</h1>
            </label>
            <input type="password" name="password"><br><br> 
              
            <button>Iniciar Sesión</button>
          </form>
      </fieldset>
  </div>
</template>

<script>
</script>
 
<style scoped>
    .search-timetables {
        padding: 40px;
    }
    fieldset {
        padding: 0 30px 40px 30px;
        
    }
    form {
        text-align: center;
    }
    label {
        display: block;
    }
    input{
        padding: 10px 10px 10px 10px;
    }
    
</style>