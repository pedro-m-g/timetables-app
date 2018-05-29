<template>
  <section class="container">
    <div class="navBar">
      <LoggedNavbar/> 
    </div>

    <div class="box">
      <h1> Registrar espacio</h1>
      <form class="form">
        <div class="test">
          <label for="fclave">Clave</label>
          <input type="text" id="fclave" name="clave">

          <label for="fnombre">Nombre</label>
          <input type="text" id="fnombre" name="clave">

          <label for="fcreditos">Capacidad</label>
          <input type="text" id="fcreditos" name="clave">
        </div>

        <div class="test2">
          <label for="ftipo">Tipo</label>
          <select id="ftipo" name="farea">
            <option value="salon">Salón</option>
            <option value="laboratorio">Laboratorio</option>
            <option value="salaComputo">Sala de computo</option>
          </select>

          <label for="fedi">Edificio</label>
          <select id="fedi" name="farea">
            <option value="E1">E1</option>
            <option value="E2">E2</option>
            <option value="E3">E3</option>
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
  background-color: #FFFFF;
  box-shadow: 5px 10px #888888;
  margin: auto;
  padding: 20px;
}

.container {
  min-height: 100vh;
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