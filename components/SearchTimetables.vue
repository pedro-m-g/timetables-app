<template>
  <div class="search-timetables">
      <fieldset>
          <form action="">
            <label>
                <h1>Carrera:</h1>
            </label>
            <select name="" id="">
                <option
                    v-for="career in careers"
                    :value="career.id"
                    :key="career.id">
                    {{ career.name }}
                </option>
            </select>

            <label>
                <h1>Periodo:</h1>
            </label>
            <select name="" id="">
                <option
                    v-for="career in careers"
                    :value="career.id"
                    :key="career.id">
                    {{ career.name }}
                </option>
            </select>
          </form>
      </fieldset>
  </div>
</template>
<script>
export default {
  data () {
      return {
          careers: [
              {
                id: 1,
                name: 'Ciencias Computacionales'  
              }
          ]
      }
  }
}
</script>

<style scoped>
    .search-timetables {
        padding: 20px;
    }
    form {
        text-align: center;
    }
    label {
        display: block;
    }
</style>
