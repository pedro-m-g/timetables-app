<template>
    <div class="row">
        <div class="col col-2">
             <LoggedTimetables />
        </div>
        <div class="col col-10">
            <Selector />
    </div>
       
    </div>
</template>
<script>
import LoggedTimetables from '@/components/LoggedTimetables'
import Selector from '@/components/Selector'
export default {
    components: {
        LoggedTimetables,
        Selector
    }
}
</script>
