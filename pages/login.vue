<template>
    <div id="formLogin">
        <div class="col col-2">
            <form-login />      
        </div>
    </div>
</template>

<script>
import FormLogin from '~/components/FormLogin.vue'

export default {
  components: {
    FormLogin
  },
  layout: 'guest'
}
</script>

<style>
    #formLogin{
        margin: 0 auto;
    }
</style>
