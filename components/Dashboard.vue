<template>
  <div class="root">
      <tabs>
        <tab
            v-for="semester in timetable.semesters"
            :key="semester.id"
            :name="'Semestre ' + semester.semester_num">
          <timetable :timetable="semester.assignments" />
        </tab>
      </tabs>
      <div class="text-right gutter-top">
        <button>Imprimir</button>
        <button>Descargar</button>
      </div>
  </div>
</template>
<script>
import Tabs from './tabs/Tabs.vue'
import Tab from './tabs/Tab.vue'

import Timetable from './timetables/Timetable.vue'
export default {
  data() {
    return {
      timetable: {
        semesters: [
          {
            id: 1,
            semester_num: 1,
            assignments: [
              {
                hour: '7:00',
                days: [
                  {
                    id: 1,
                    subject: 'Reingenieria de Procesos'
                  },
                  {
                    id: 2,
                    subject: 'Reingenieria de Procesos'
                  },
                  {
                    id: 3,
                    subject: 'Reingenieria de Procesos'
                  },
                  {
                    id: 4,
                    subject: 'Reingenieria de Procesos'
                  },
                  {
                    id: 5,
                    subject: 'Reingenieria de Procesos'
                  },
                  {
                    id: 6,
                    subject: 'Reingenieria de Procesos'
                  }
                ]
              },
              {
                hour: '8:00',
                days: [
                  {
                    id: 7,
                    subject: 'Reingenieria de Procesos'
                  },
                  {
                    id: 8,
                    subject: ''
                  },
                  {
                    id: 9,
                    subject: ''
                  },
                  {
                    id: 10,
                    subject: 'Reingenieria de Procesos'
                  },
                  {
                    id: 11,
                    subject: 'Reingenieria de Procesos'
                  },
                  {
                    id: 12,
                    subject: 'Reingenieria de Procesos'
                  }
                ]
              }
            ]
          }
        ]
      }
    }
  },
  components: {
    Tabs,
    Tab,
    Timetable
  }
}
</script>

<style scoped>
.root {
  padding: 40px;
}
</style>
