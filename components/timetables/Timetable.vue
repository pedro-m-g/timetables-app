<template>
  <div>
      <table>
          <thead>
              <tr>
                  <th>Hora</th>
                  <th>Lunes</th>
                  <th>Martes</th>
                  <th>Miércoles</th>
                  <th>Jueves</th>
                  <th>Viernes</th>
                  <th>Sábado</th>
              </tr>
          </thead>
          <tbody>
              <tr
                v-for="assignment in timetable"
                :key="assignment.id">
                  <td>{{ assignment.hour }}</td>
                  <td
                    v-for="day in assignment.days"
                    :key="day.id">
                    {{ day.subject }}
                  </td>
              </tr>
          </tbody>
      </table>
  </div>
</template>
<script>
export default {
    props: {
        timetable: {
            required: true
        },
        readOnly: {
            default: false
        }
    }
}
</script>
