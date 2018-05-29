<template>
  <div class="">
      <!--<fieldset> -->
          <h4 style="text-align:center;">Ver Horarios</h4>
          <div id="contenedor">
              <select class="item">
                  <option selected disabled>Carrera</option>
                <option
                    v-for="career in careers"
                    :value="career.id"
                    :key="career.id">
                    {{ career.name }}
                </option>
            </select>
          <select class="item">
              <option selected disabled>Periodo</option>
                <option
                    v-for="period in periods"
                    :value="period.year + '_' + period.period"
                    :key="period.year + '_' + period.period">
                    {{ period.year }} - {{ period.period }}
                </option>
            </select>
          <select>
              <option selected disabled>Semestre</option>
                  <option v-for="semester in semesters"
                          :value="semester.id"
                          :key="semester.key">
                      {{semester.name}}
                </option>
            </select>
        </div>
         <!-- <form action="">
            <label style="margin-top:25px;">Carrera</label><br>
            <select>
                <option
                    v-for="career in careers"
                    :value="career.id"
                    :key="career.id">
                    {{ career.name }}
                </option>
            </select><br><br>

            <label>Periodo</label><br>
            <select>
                <option
                    v-for="period in periods"
                    :value="period.year + '_' + period.period"
                    :key="period.year + '_' + period.period">
                    {{ period.year }} - {{ period.period }}
                </option>
            </select><br><br>
              <label>Semestre</label>
              <select>
                  <option v-for="semester in semesters"
                          :value="semester.id"
                          :key="semester.key">
                      {{semester.name}}
                </option>
            </select>
          </form> -->
     <!-- </fieldset>-->
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
              },
              {
                id: 2,
                name: 'Matemáticas Aplicadas'
              },
              {
                id: 3,
                name: 'Física'  
              },
              {
                id: 4,
                name: 'Biología'  
              },
              {
                  id: 5,
                  name: 'Tronco Común'
              }
          ],
          periods: [
              {
                  year: 2018,
                  period: 1
              },
              {
                  year: 2018,
                  period: 2
              },
              {
                  year: 2017,
                  period: 1
              },
              {
                  year: 2017,
                  period: 2
              },
              {
                  year: 2016,
                  period: 1
              },
              {
                  year: 2016,
                  period: 2
              },
          ],
          semesters: [
              {
                  id: 1,
                  name: 'Sem VII'
              },
              {
                  id: 2,
                  name: 'Sem II'
              },
              {
                  id: 3,
                  name: 'Sem III'
              },
              {
                  id: 4,
                  name: 'Sem IV'
              },
              {
                  id: 5,
                  name: 'Sem V'
              },
              {
                  id: 6,
                  name: 'Sem VI'
              },
              {
                  id: 7,
                  name: 'Sem VII'
              },
              {
                  id: 8,
                  name: 'Sem VIII'
              },
              
          ]
      }
  }
}
</script>

<style scoped>
    /*.search-timetables {
        padding: 40px;
        width: 400px;
        float: right;
    }
    fieldset {
        padding: 0 30px 40px 30px;
    }
    form {
        text-align: center;
    }
    label {
        display: block;
    }*/
    #contenedor select {
        display: inline-block;
    }
    .item{
        /* float: right; */
    }
</style>
