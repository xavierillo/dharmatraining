<template>
<div id="app">
	<div v-bind:style="style_object" v-if="page == 0">
		<div class="container">
			<div class="row">
				<div class="col-12 text-white menu_font_built_bold text-center p-4">
					<a :href="data.facebook" class="btn text-white pl-2" target="_black" ><i class="fab fa-facebook" style="font-size: 25px;"></i></a>
					<a :href="data.whatsapp" class="btn text-white pl-2" target="_black" ><i class="fab fa-whatsapp" style="font-size: 25px;"></i></a>
					<a :href="data.instagram" class="btn text-white pl-2" target="_black" ><i class="fab fa-instagram" style="font-size: 25px;"></i></a>
					<a :href="data.maps" class="btn text-white pl-2" target="_black" ><i class="fas fa-map-marker-alt pr-2" style="font-size: 25px;"></i><span style="font-size: 15px;">{{ data.direction }}</span></a>
				</div>
			</div>
		</div>
		<div class="c-app flex-row align-items-center" style="margin-top: -90px;"> 
			<div class="container">
				<div class="row">
					<div class="col-12 text-white text-center">	
						<div class="menu_font_built_bold h3 text-white pt-4 mt-4 letter-spacing-0">Prove <span class="text-pink">your</span> fitness</div>
					</div>
					<div class="col-12 text-center pb-4 pt-1">
						<img src="./assets/images/dharma_300px.png" @click="page=0" style="cursor: pointer;">
					</div>
					<div class="col-12 text-center pt-4">
						<button type="button" class="btn btn-lg btn-pink m-2"><strong>Clase de prueba</strong></button>
						<button type="button" class="btn-lg btn btn-pink m-2" @click="page=1"><strong>Inicio</strong></button>
					</div>
				</div>
			</div>
		</div>
	</div>
	<div v-if="page == 1"> 
		<div v-bind:style="style_object_2">
			<div class="container-fluid navbar navbar-dark navbar-expand-md">
				<div class="row  w-100">
					<div class="col-12 d-md-none d-sm-block text-white menu_font_built_bold text-center" style="font-size: 12px;">
						<a :href="data.facebook" class="btn text-white pl-2" target="_black" ><i class="fab fa-facebook"></i></a>
						<a :href="data.whatsapp" class="btn text-white pl-2" target="_black" ><i class="fab fa-whatsapp"></i></a>
						<a :href="data.instagram" class="btn text-white pl-2" target="_black" ><i class="fab fa-instagram"></i></a>
						<a :href="data.maps" class="btn text-white pl-2" target="_black" ><i class="fas fa-map-marker-alt pr-2"></i>{{ data.direction }}</a>
					</div>
					<div class="col-2 text-center">
						<img class="navbar-brand" src="./assets/images/dharma_100px.png" @click="page=0" style="cursor: pointer;">
					</div>
					<div class="col-7 mt-3">
						<div class="collapse navbar-collapse justify-content-lg-center">
							<ul class="navbar-nav menu_font_built_bold letter-spacing-0">
								<li class="nav-item">
									<a class="nav-link" href="#process">Inicio</a>
								</li>
								<li class="nav-item">
									<b-nav-item-dropdown text="Programa" right>
										<b-dropdown-item href="#">Crossfit</b-dropdown-item>
										<b-dropdown-item href="#">Open box</b-dropdown-item>
									</b-nav-item-dropdown>
								</li>
								<li class="nav-item">
								  <a class="nav-link" href="#popular-destinations">Horarios</a>
								</li>
								<li class="nav-item">
								  <a class="nav-link" href="#request-quote">Clases de prueba</a>
								</li>
								<li class="nav-item">
								  <a class="nav-link" href="#request-quote">Contacto y como llegar</a>
								</li>
							</ul>
						</div>
					</div>
					<div class="col-3 ml-auto ml-0">
						<div class="collapse navbar-collapse row text-white text-white menu_font_built_bold text-center mt-2">
							<div class="col-12" style="font-size: 16px;">
								<a :href="data.maps" class="btn text-white p-0" target="_black" >
									<i class="fas fa-map-marker-alt pr-2"></i>{{ data.direction }}
								</a>
							</div>
							<div class="col-12">
								<a :href="data.facebook" class="btn text-white" target="_black" ><i class="fab fa-facebook"></i></a>
								<a :href="data.whatsapp" class="btn text-white pl-2" target="_black" ><i class="fab fa-whatsapp"></i></a>
								<a :href="data.instagram" class="btn text-white pl-2" target="_black" ><i class="fab fa-instagram"></i></a>
							</div>
						</div>
						<div class="text-right h-100 d-flex" style="justify-content: center;  align-items: center;">
							<button class="navbar-toggler" v-b-toggle.sidebar-backdrop data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
								<span class="navbar-toggler-icon"></span>
							</button>
							<b-sidebar id="sidebar-backdrop" :title="title_page" :backdrop-variant="variant" backdrop shadow>
							  <div class="px-3 py-2">
								<ul class="menu_font_built_bold letter-spacing-2 text-left">
								<li class="nav-item w-100">
									<a class="nav-link" href="#process">Inicio</a>
								</li>
								<li class="nav-item w-100">
									<b-nav-item-dropdown text="Programa" right>
										<b-dropdown-item href="#">Crossfit</b-dropdown-item>
										<b-dropdown-item href="#">Open box</b-dropdown-item>
									</b-nav-item-dropdown>
								</li>
								<li class="nav-item w-100">
								  <a class="nav-link" href="#popular-destinations">Horarios</a>
								</li>
								<li class="nav-item w-100">
								  <a class="nav-link" href="#request-quote">Clases de prueba</a>
								</li>
								<li class="nav-item w-100">
								  <a class="nav-link" href="#request-quote">Contacto y como llegar</a>
								</li>
							</ul>
							  </div>
							</b-sidebar>
						</div>
					</div>
				</div>
			</div>
			<div class="c-app flex-row align-items-center" style="margin-top: -90px;"> 
				<div class="container">
					<div class="row">
						<div class="col"></div>
						<div class="col-12 col-sm-12 col-md-8 col-lg-6 col-xl-6 text-white text-center pl-4 pr-4">
							<div class="menu_font_built_bold h3 text-white letter-spacing-0">
							TEXTO 1: VISION. BREVE DESCRIPCÓN DEL SERVICIO HAIENDO HINCAPIE EN IDEA DE DESCIPLINA INEGRAL, QUIZÁS DESMITIFICAR IDEA DE CROSSFIT COMO "DEPORTE RUDO-MILITAR"</div>
						</div>
						<div class="col"></div>
						<div class="col-12 text-center pt-4">
							<button type="button" class="btn btn-lg btn-pink m-2 "><strong class="text-uppercase">Clase de prueba</strong></button>
							<button type="button" class="btn-lg btn btn-pink m-2 "><strong class="text-uppercase">Te contactamos</strong></button>
						</div>
					</div>
				</div>
			</div>
		</div>
	 
		<div class="container-full" style="background-color: #e6ebf0">
			<div class="row p-4">
				<div class="col-4 text-center pt-4">
					<img src="./assets/images/dharma_300px.png" @click="page=0" style="cursor: pointer;">
				</div>
				<div class="col-8 ">
					<div class="h2 text-body pt-4 mt-4 letter-spacing-0 text-uppercase"><strong>Camila contreras</strong></div>
					<h3> Brece presentacion entrenadora. formación y experiencia</h3>
				</div>
			</div>
		</div>

		<div class="container-full" style="background-color: #f4f5f6">
			<div class="row p-4">
				<div class="col-12 text-center">
					<div class="h3 text-body pt-4 mt-4 letter-spacing-0 bold text-uppercase"><strong>sigue a nuestra comunidad</strong></div>
				</div>
				<div class="col-4 text-center pt-4">
					<img src="./assets/images/dharma_300px.png" @click="page=0" style="cursor: pointer;">
				</div>
				<div class="col-8">
					<div class="h3 text-body pt-4 mt-4 letter-spacing-0">sigue a nuestra comunidad</div>
					<h3> Brece presentacion entrenadora. formación y experiencia</h3>
				</div>
			</div>
		</div>
		 
	</div>

	<footer class="footer mt-auto py-3">
		  <div class="container">
		    <span class="text-muted">Place sticky footer content here.</span>
		  </div>
	</footer>
</div>
</template>
<script type="text/javascript">
	export default {
		name: 'app',
		data () {
			return {
				data: {
					name: 'dharma training',
					direction: 'Los nísperos 43, La Serena',
					maps: 'https://goo.gl/maps/dryW6WmTtVmJAUn56',
					whatsapp: 'https://wa.me/+56988888888',
					facebook: 'https://www.facebook.com/dharmatraining',
					instagram: 'https://www.instagram.com/dharma_training/',
				},
				title_page: 'Dharma training',
				variant: 'dark',
				style_object: {
    				'background-size': 'cover',
					'background-image': `url(${require('./assets/images/enmascarar_grupo_4.png')})`
				},
				style_object_2: {
    				'background-size': 'cover',
					'background-image': `url(${require('./assets/images/enmascarar_grupo_2.png')})`
				},
				page: 1
			}
		}
	}
</script>