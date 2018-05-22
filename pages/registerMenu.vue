<template>
	<section class="container">
		<div class="navBar">
			<LoggedNavbar/>	
		</div>

		<div class="box">
			<h1> Registrar </h1>
			<div class="">
				<a href="#"><div class="grid-item">Aulas</div></a>
				<a href="/Forms/academicoForm"><div class="grid-item">Academicos</div></a>
				<a href="/Forms/MateriasForm"><div class="grid-item">Materias</div></a>
				<div class="grid-item">...</div>

			</div>
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

h1{
  padding-bottom: 15px;
  color: #B49A3D;
}
	

.box{
  border: 4px solid #007141;
  border-radius: 25px;
  width: 40%;
  height: 40%;
  background-color: #FFFFF;
  box-shadow: 5px 10px #888888;
  margin: auto;
  padding: 10px;
}

.container {
  min-height: 100vh;
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

.grid-item{
	margin:0 1% 1% 0;
	float:left;
	clear:none;
	width:48%;
	height:100%;
	border:3px solid  #007141;
	border-radius: 25px;
}

</style>