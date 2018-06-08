<template>
  <section class="container">
    <div class="box">
      <h1> Registrar Academico</h1>
      <form class="form">

        <div class="test">

          <label for="fnempleado">No. de Empleado</label>
          <input type="text" id="fnempleado" name="clave">
            
          <label for="fnombre">Nombre</label>
          <input type="text" id="fnombre" name="clave">

          <label for="fapellido">Apellido</label>
          <input type="text" id="fapellido" name="clave">
        </div>


        <div class="test">

          <label for="fcorreo">Correo</label>
          <input type="text" id="fcorreo" name="clave">

          <label for="ftp">Teléfono particula</label>
          <input type="text" id="ftp" name="clave">

          <label for="fto">Teléfono oficina</label>
          <input type="text" id="fto" name="clave">
        </div>

        <div class="test2">

          <label for="fcategoria">Categoría</label>
          <select id="fcategoria" name="categoria">
            <option value="asignatura">Asignatura</option>
            <option value="planta">Planta</option>
          </select>

        

          <label for="fplan">Plan</label>
          <select id="plan" name="fplan">
            <option value="1">2016</option>
          </select>

        </div>
        <input class="saveButton" type="submit" name="" value="Guardar">
      </form>

    </div>
  </section>
</template>

<script>
import LoggedNavbar from '~/components/LoggedNavbar.vue'
export default {
  components: {
      LoggedNavbar
  }
};
</script>


<style scoped>

.saveButton{
  float: right;
  background-color: #007141;
  border: none;
  font-size: 16px;
  margin: 4px 2px;
  padding: 10px 32px;
  color: white;

}

.test{
  column-count: 3;
}

.test2{
  column-count: 2;
}

input, label {
    display:block;
}

h1{
  padding-bottom: 15px;
  color: #B49A3D;
}
  

.box{
  border: 4px solid #007141;
  border-radius: 25px;
  width: 40%;
  height: 40%;
  background-color: white;
  box-shadow: 5px 10px #888888;
  margin: auto;
  padding: 20px;
}

.container {
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.navBar{
  position: absolute;
  top: 0px;
  left: 0px;
  width: 100%;
}

input[type=text], select {
    width: 100%;
    padding: 5px 20px;
    margin: 8px 2;
    display: inline-block;
    border: 1px solid #ccc;
    border-radius: 4px;
}

</style>