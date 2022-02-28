<script >
import 'animate.css'
export default{
	name: 'app',
	data (){
		return{
			showDados : false,
			showIncluir: false,
			options:[{id:1, descricao: 'Hospital Albert Einstein.'},
			{id:2, descricao:'Hospital Sírio-Libanês.'},
			{id:3, descricao: 'Hospital São Luiz.'},
			{id:4, descricao: 'Hospital Samaritano.'}]
		}
	}
}
</script>

<template>
	<div class="">
		<div class="border-bottom pb-2">
			<nav class="navbar  navbar-light  container-fluid px-3">
				<a class="navbar-brand" href="#">Prototipo</a>
				<button class="navbar-toggler color-dark d-md-none" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
					<span class="navbar-toggler-icon color-dark"></span>
				</button>
			</nav>
		</div>
		<div class="mt-0 row text-center py-2 shadow-sm" style="background:#fafafa;">
			<h5 class="col-12 ">Prototipo Plano de Saúde</h5>
			<ul class="d-flex   justify-content-around text-center">
				<li class="item-active item pb-2 px-1">Opção 1</li>
				<li class="pb-2 item">Opção 2</li>
				<li class="pb-2 item">Opção 3</li>
			</ul>
		</div>
		<div class="mt-3 shadow-sm py-4 ">
			<div class="container-fluid p-0 ">
				<div class="row d-flex px-3">
					<span class="col-9 col-md-10" style="font-size:1.5em"><i class="fas fa-user me-3"></i><span> Seus Dados</span></span>
					<transition enter-active-class="animate__animated animate__fadeIn"  appear>
						<button v-if="!showDados" @click="showDados = !showDados" class="btn btn-outline-success ps-0 pe-0 col-3 col-md-2 animate__animated animate__fadeIn "><i class="fa fa-pencil me-1"></i> Alterar</button>
						<button v-else @click="showDados = !showDados" class="btn btn-success ps-0 pe-0 col-3 col-md-2 animate__animated animate__fadeIn "><i class="fa fa-check me-1"></i> Salvar</button>
					</transition>
				</div>
			</div>
			<transition  enter-active-class="animate__animated animate__fadeIn"  appear>
				<div v-if="showDados" class="row displau-block px-3 d-flex justify-content-between mt-3">
					<div class="col-6">
						<small class="text-secondary">Nome</small>
						<input type="text" class="form-control">
					</div>
					<div class="col-6">
						<small class="text-secondary">SobreNome</small>
						<input type="text" class="form-control">
					</div>
					<div class="col-12">
						<small class="text-secondary">Email</small>
						<input type="text" class="form-control">
					</div>
					<div class="col-12">
						<small class="text-secondary">Data de nascimento</small>
						<input type="date" class="form-control">
					</div>
					
				</div>
			</transition>
		</div>
		<div class="mt-3 py-4 shadow-sm">
			<div class="container-fluid p-0 ">
				<div class="row d-flex px-3">
					<span class="col-9 col-md-10" style="font-size:1.5em"><i class="fas fa-hospital me-3"></i><span>Informações do Plano</span></span>
					<transition enter-active-class="animate__animated animate__fadeIn"  appear>
						<button v-if="!showIncluir" @click="showIncluir = !showIncluir" class="btn btn-outline-success ps-0 pe-0 col-3 col-md-2 animate__animated animate__fadeIn "><i class="fa fa-plus me-1"></i> Inlcuir</button>
						<button v-else @click="showIncluir = !showIncluir" class="btn btn-primary ps-0 pe-0 col-3 col-md-2 animate__animated animate__fadeIn "><i class="fa fa-check me-1"></i> Salvar</button>
					</transition>
				</div>
			</div>
			<transition  enter-active-class="animate__animated animate__fadeIn"  appear>
				<div v-if="showIncluir" class="row displau-block px-3 d-flex justify-content-between mt-3">
					<div class="col-12">
						<small class="text-secondary">Instituição Desejada</small>
						<select class="form-select" id="">
							<option v-for="(option, index) in options" :key="index">{{option.descricao}}</option>
						</select>
					</div>
					<div class="col-6">
						<small class="text-secondary">Dependentes</small>
						<select class="form-select" id="">
							<option value="1">Sim</option>
							<option value="2">Não</option>
						</select>
					</div>
					<div class="col-12">
						<small class="text-secondary">Email</small>
						<input type="text" class="form-control">
					</div>
					<div class="col-12">
						<small class="text-secondary">Data de nascimento</small>
						<input type="date" class="form-control">
					</div>
					
				</div>
			</transition>
		</div>
	</div>
</template>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
ul li{
	list-style: none;
}
.item{
	cursor: pointer;
}
.item-active{
	border-bottom: 2px solid green;
	border-radius: 2px;
	color: green;
	font-weight: 600;
}
#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
