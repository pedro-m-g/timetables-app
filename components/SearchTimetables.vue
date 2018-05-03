<template>
  <div class="search-timetables">
      <fieldset>
          <form action="">
            <label>
                <h1>Carrera:</h1>
            </label>
            <select>
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
            <select>
                <option
                    v-for="period in periods"
                    :value="period.year + '_' + period.period"
                    :key="period.year + '_' + period.period">
                    {{ period.year }} - {{ period.period }}
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
          ],
          periods: [
              {
                  year: 2018,
                  period: 2
              },
              {
                  year: 2018,
                  period: 1
              },
              {
                  year: 2017,
                  period: 2
              },
              {
                  year: 2017,
                  period: 1
              }
          ]
      }
  }
}
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
</style>
