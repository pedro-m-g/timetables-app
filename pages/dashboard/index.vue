<template>
    <div class="row">
        <div class="col col-2">
            <Selector />
             <LoggedTimetables />
        </div>
        
       
    </div>
</template>
<script>
import LoggedTimetables from '@/components/LoggedTimetables'
    import Selector from '@/components/Selector'
export default {
    components: {
        Selector,
        LoggedTimetables
    }
}
</script>
