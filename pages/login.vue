<template>
  <section class="container">
    <div class="navBar">
      <GuestNavbar/>
    </div>
    <div class="loginbox">
      <div>
        <h1>Iniciar sesión</h1>
        <div class="loginform">
          <form @submit.prevent="login">
            <input v-model="usuario" placeholder="Usuario">
            <input v-model="password" type="password" placeholder="Contraseña">
            <div class="loginBottom">
              <a href="#">¿Olvidaste tu contraseña?</a>
              <button type="submit">Iniciar sesión</button>
            </div>
          </form>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import GuestNavbar from '~/components/GuestNavbar.vue'
export default {
  components: {
      GuestNavbar
  },
  data () {
    return {
      credentials: {
        email: '',
        password: ''
      }
    }
  },
  methods: {
    login () {
      this.$router.push('/dashboard')
    }
  }
};
</script>

<style scoped>

.navBar{
  position: absolute;
  top: 0px;
  left: 0px;
  width: 100%;
}

/* Login */
.loginbox{
  border: 4px solid #007141;
  border-radius: 25px;
  width: 40%;
  height: 40%;
  background-color: #FFFFF;
  box-shadow: 5px 10px #888888;
}

.loginBottom{
  padding-bottom: 20px;
}

a{
  float: left;
}

button{
  float: right;
  background-color: #007141;
  border: none;
  font-size: 16px;
  margin: 4px 2px;
  padding: 10px 32px;
  color: white;
}

h1{
  padding-bottom: 15px;
  color: #B49A3D;
}

input{
    width: 100%;
    padding: 12px 20px;
    margin: 8px 0;
    box-sizing: border-box;
    border: none;
    background-color: #EAEAEA;
    color: black;
}

.loginform{
  margin: auto;
  width:80%;
  height: 80%;
  padding-bottom: 15px;
}

.container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; /* 1 */
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
