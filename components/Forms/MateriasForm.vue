<template>
  <section class="container">
    <div class="box">
      <h1> Registrar Materia</h1>
      <form @submit.prevent="$emit('submit', $event)" class="form">
        

        <label for="fnombre">Nombre</label>
        <input type="text" id="fnombre" name="clave">

        <div class="test">

          <label for="fnombrec">Nombre corto</label>
          <input type="text" id="fnombrec" name="clave">

          <label for="fclave">Clave</label>
          <input type="text" id="fclave" name="clave">

          <label for="fcreditos">Creditos</label>
          <input type="text" id="fcreditos" name="clave">
        </div>

        <div class="test">

          <label for="fhc">Horas clase</label>
          <input type="text" id="fhc" name="clave">

          <label for="fhl">Horas laboratorio</label>
          <input type="text" id="fhl" name="clave">

          <label for="fht">Horas taller</label>
          <input type="text" id="fht" name="clave">
        </div>

        <div class="test">

          <label for="farea">Área</label>
          <select id="area" name="farea">
            <option value="basica">Basica</option>
            <option value="disciplinaria">Disciplinaria</option>
            <option value="terminal">Terminal</option>
          </select>

          <label for="fsemestre">Semestre</label>
          <select id="semestre" name="fsemestre">
            <option value="1">I</option>
            <option value="2">II</option>
            <option value="3">III</option>
            <option value="3">IV</option>
            <option value="3">V</option>
            <option value="3">VI</option>
            <option value="3">VII</option>
            <option value="3">VIII</option>
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