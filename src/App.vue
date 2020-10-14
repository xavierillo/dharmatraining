<template>
<div id="app">
	<div v-bind:style="style_object" v-if="page == 0">
		<div class="container">
			<div class="row m-0">
				<div class="col-12 text-white menu_font_built_bold text-center p-4">
					<a :href="data.facebook" class="btn text-white pl-2" target="_black" ><i class="fab fa-facebook" style="font-size: 25px;"></i></a>
					<a :href="data.whatsapp" class="btn text-white pl-2" target="_black" ><i class="fab fa-whatsapp" style="font-size: 25px;"></i></a>
					<a :href="data.instagram" class="btn text-white pl-2" target="_black" ><i class="fab fa-instagram" style="font-size: 25px;"></i></a>
					<a :href="data.maps" class="btn text-white pl-2" target="_black" ><i class="fas fa-map-marker-alt pr-2" style="font-size: 25px;"></i><span style="font-size: 15px;">{{ data.direction }}</span></a>
				</div>
			</div>
		</div>
		<div class="c-app flex-row align-items-center" style="margin-top: -90px; min-height: 100vh;"> 
			<div class="container">
				<div class="row m-0">
					<div class="col-12 text-white text-center">	
						<div class="menu_font_built_bold h3 text-white pt-4 mt-4 letter-spacing-0">Prove <span class="text-pink">your</span> fitness</div>
					</div>
					<div class="col-12 text-center pb-4 pt-1">
						<img src="./assets/images/dharma_300px.png" @click="page=0" class="c-pointer">
					</div>
					<div class="col-12 text-center pt-4">
						<a target="_black" class="btn btn-lg btn-pink m-2" :href="data.contact_me"><strong class="text-uppercase">Clase de prueba</strong></a>
						<button type="button" class="btn-lg btn btn-pink m-2" @click="page=1"><strong>Inicio</strong></button>
					</div>
				</div>
			</div>
		</div>
	</div>
	<div v-if="page >= 1"> 
		<!-- centana principal con fondo  -->
		<div v-bind:style="style_object_2">
			<div class="container-fluid navbar navbar-dark navbar-expand-md">
				<div class="row m-0">
					<div class="col-12 d-md-none d-sm-block text-white menu_font_built_bold text-center" style="font-size: 12px;">
						<a :href="data.facebook" class="btn text-white pl-2" target="_black" ><i class="fab fa-facebook"></i></a>
						<a :href="data.whatsapp" class="btn text-white pl-2" target="_black" ><i class="fab fa-whatsapp"></i></a>
						<a :href="data.instagram" class="btn text-white pl-2" target="_black" ><i class="fab fa-instagram"></i></a>
						<a :href="data.maps" class="btn text-white pl-2" target="_black" ><i class="fas fa-map-marker-alt pr-2"></i>{{ data.direction }}</a>
					</div>
					<div class="col-2 text-center">
						<img class="navbar-brand" src="./assets/images/dharma_100px.png" @click="page=0" style="z-index: 999;cursor: pointer;">
					</div>
					<div class="col-7 mt-3 d-sm-none d-md-block">
						<div class="collapse navbar-collapse justify-content-lg-center">
							<ul class="navbar-nav menu_font_built_bold letter-spacing-0">
								<li class="nav-item">
									<a class="nav-link c-pointer" @click="change_page(1)">Inicio</a>
								</li>
								<li class="nav-item">
									<b-nav-item-dropdown text="Programa" right>
										<b-dropdown-item @click="change_page(2)">Crossfit</b-dropdown-item>
										<b-dropdown-item @click="change_page(3)">Open box</b-dropdown-item>
									</b-nav-item-dropdown>
								</li>
								<li class="nav-item">
								  <a class="nav-link c-pointer" @click="change_page(4)">Horarios</a>
								</li>
								<li class="nav-item">
								  <a class="nav-link c-pointer" @click="change_page(5)">Clases de prueba</a>
								</li>
								<li class="nav-item">
								  <a class="nav-link c-pointer" @click="change_page(6)">Contacto y como llegar</a>
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
										<a class="nav-link c-pointer" v-b-toggle.sidebar-backdrop @click="change_page(1)">Inicio</a>
									</li>
									<li class="nav-item w-100">
										<b-nav-item-dropdown text="Programa" right>
											<b-dropdown-item v-b-toggle.sidebar-backdrop @click="change_page(2)">Crossfit</b-dropdown-item>
											<b-dropdown-item v-b-toggle.sidebar-backdrop @click="change_page(3)">Open box</b-dropdown-item>
										</b-nav-item-dropdown>
									</li>
									<li class="nav-item w-100">
									  <a class="nav-link c-pointer" v-b-toggle.sidebar-backdrop @click="change_page(4)">Horarios</a>
									</li>
									<li class="nav-item w-100">
									  <a class="nav-link c-pointer" v-b-toggle.sidebar-backdrop @click="change_page(5)">Clases de prueba</a>
									</li>
									<li class="nav-item w-100">
									  <a class="nav-link c-pointer" v-b-toggle.sidebar-backdrop @click="change_page(6)">Contacto y como llegar</a>
									</li>
								</ul>
							  </div>
							</b-sidebar>
						</div>
					</div>
				</div>
			</div>
			<!-- inicio 1 -->
			<div v-if="page == 1" class="c-app flex-row align-items-center"> 
				<div class="container">
					<div class="row m-0 text-white">
						<div class="col-12 col-sm-6 col-md-6 pb-4">
 							<h4  class="menu_font_built_bold h3 text-white letter-spacing-0"><i class="fas fa-users"></i> UNA DISCIPLINA PARA TODOS</h4>
 							<h6 class="text-justify">¡No importan tu tamaño o tus medidas! Entendemos el CrossFit como una experiencia inclusiva que puede ayudar a cualquiera que desee mejorar su vida.</h6>
 						</div>
 						<div class="col-12 col-sm-6 col-md-6 pb-4">
 							<h4  class="menu_font_built_bold h3 text-white letter-spacing-0"><i class="fas fa-balance-scale"></i> DEPORTE INTEGRAL</h4>
 							<h6 class="text-justify">Promovemos tanto la salud física como la mental y espiritual a través del acondicionamiento físico (CrossFit).</h6>
 						</div>
 						<div class="col-12 col-sm-6 col-md-6 pb-4">
 							<h4  class="menu_font_built_bold h3 text-white letter-spacing-0"><i class="fas fa-heart"></i> SÉ PARTE DE UNA COMUNIDAD</h4>
 							<h6 class="text-justify">Creemos en la importancia de los vínculos entre las personas y por eso fomentamos un ambiente de confianza y apoyo mutuo. ¡Los logros de uno son los logros de todos!</h6>
 						</div>
 						<div class="col-12 col-sm-6 col-md-6 pb-4">
 							<h4  class="menu_font_built_bold h3 text-white letter-spacing-0"><i class="fas fa-walking"></i> ENTRENAMIENTO PERSONALIZADO</h4>
 							<h6 class="text-justify">Nuestras clases de CrossFit están ideadas para ti considerando tus fortalezas y debilidades. Te ayudaremos a alcanzar tu propia meta.</h6>
 						</div>
					</div>
					<div class="row m-0 text-white  pt-4">
						<div class="col-12 text-center">
							<a target="_black" class="btn btn-lg btn-pink m-2" :href="data.contact_me"><strong class="text-uppercase">Clase de prueba</strong></a>
							<a target="_black" class="btn-lg btn btn-pink m-2" :href="data.proof_class"><strong class="text-uppercase">Te contactamos</strong></a>
						</div>
					</div>
				</div>
			</div>
			<div v-if="page == 2" class="c-app flex-row align-items-center"> 
				<div class="container">
					<div class="row m-0">
						<div class="col-12 text-white text-center pl-4 pr-4 d-sm-none">
							<strong class="display-4 font_third_rail text-pink letter-spacing-1">Crossfit</strong>
							<div class="h5 text-white letter-spacing-0 font-weight-bold">{{ data.text_crossfit }}</div>
						</div>
						<div class="col-12 text-white text-center pt-4 pb-4 d-sm-none">
							<small class="h5"> sal de la rutina a través de movimientos constantemente variados y a eso súmale una ejecución a alta intensidad ¿que obtienes? resultados</small>
						</div>
						<div class="col-12 text-white text-center pl-4 pr-4 d-none d-sm-block">
							<strong class="display-1 font_third_rail text-pink letter-spacing-1">Crossfit</strong>
							<div class="h2 text-white letter-spacing-0 font-weight-bold">{{ data.text_crossfit }}</div>
						</div>
						<div class="col-12 text-white text-center pt-4 pb-4 d-none d-sm-block">
							<small class="h4"> sal de la rutina a través de movimientos constantemente variados y a eso súmale una ejecución a alta intensidad ¿que optienes? resultados</small>
						</div>
						<div class="col-12 text-center pt-4">
							<a target="_black" class="btn btn-lg btn-pink m-2" :href="data.contact_me"><strong class="text-uppercase">Clase de prueba</strong></a>
							<a target="_black" class="btn-lg btn btn-pink m-2" :href="data.proof_class"><strong class="text-uppercase">Te contactamos</strong></a>
						</div>
					</div>
				</div>
			</div>
			<div v-if="page == 3" class="c-app flex-row align-items-center"> 
				<div class="container">
					<div class="row m-0">
						<div class="col-12 pt-4 text-white text-center d-sm-none">
							<strong class="display-4 font_third_rail text-pink letter-spacing-1">Open Box</strong>
							<div class="h4 text-white letter-spacing-0 font-weight-bold">{{ data.text_open_box }}</div>
						</div>
						<div class="col-12 pt-4 text-white text-center d-none d-sm-block">
							<strong class="display-1 font_third_rail text-pink letter-spacing-1">Open Box</strong>
							<div class="h2 text-white letter-spacing-0 font-weight-bold">{{ data.text_open_box }}</div>
						</div>
						<div class="col-12 text-white text-center pt-4 pb-4">
							<small class="h5">Durante el open box siempre tendrán la ayuda y supervision de un entrenador, pero eso no significa que sea una clase individual, tampoco una clase normal con el entrenador al frente</small>
						</div>
						<div class="col-12 text-center pt-4">
							<a target="_black" class="btn btn-lg btn-pink m-2" :href="data.contact_me"><strong class="text-uppercase">Clase de prueba</strong></a>
							<a target="_black" class="btn-lg btn btn-pink m-2" :href="data.proof_class"><strong class="text-uppercase">Te contactamos</strong></a>
						</div>
					</div>
				</div>
			</div>
			<div v-if="page == 4" class="c-app flex-row align-items-center"> 
				<div class="container">
					<div class="row m-0">
						<div class="col-12 text-white text-center pl-4 pr-4">
							<div class="row">
								<div class="ol-12 col-sm-12 col-md-6 col-lg-6 col-xl-6">
									<h1 class="text-pink font-weight-bold text-uppercase">Horarios Crossfit</h1>
									<h3>(Max. 6 personas por clase)</h3>
									<h3>Lunes a viernes</h3>
									<h3>9:00 a 10:00</h3>
									<h3>18:30 a 19:30</h3>
									<h3>19:30 a 20:30</h3>
								</div>
								<div class="ol-12 col-sm-12 col-md-6 col-lg-6 col-xl-6">
									<h1 class="text-pink font-weight-bold text-uppercase">Horarios Open Box</h1>
									<h3>(Max. 6 personas por bloque)</h3>
									<h3>Lunes a viernes</h3>
									<h3>10:00 a 13:00</h3>
									<h3>13:00 a 15:00</h3>
									<h3>15:00 a 18:00</h3>
								</div>
							</div>
						</div>
						<div class="col-12 text-center pt-4">
							<a target="_black" class="btn btn-lg btn-pink m-2" :href="data.contact_me"><strong class="text-uppercase">Clase de prueba</strong></a>
							<a target="_black" class="btn-lg btn btn-pink m-2" :href="data.proof_class"><strong class="text-uppercase">Te contactamos</strong></a>
						</div>
					</div>
				</div>
			</div>
			<div v-if="page == 5" class="c-app flex-row align-items-center"> 
				<div class="container">
					<div class="row m-0">
						<div class="col-12 pt-4 text-white text-center d-sm-none">
							<strong class="display-4 font_third_rail text-pink letter-spacing-1">Clase de prueba</strong>
							<div class="h5 text-white letter-spacing-0 font-weight-bold">¡Solo necesitas las ganas!</div>
						</div>
						<div class="col-12 pt-4 text-white text-center d-none d-sm-block">
							<strong class="display-1 font_third_rail text-pink letter-spacing-1">Clase de prueba</strong>
							<div class="h3 text-white letter-spacing-0 font-weight-bold">¡Solo necesitas las ganas!</div>
						</div>
						<div class="col-12 text-white text-center pt-4 pb-4">
							<small class="h4">cuando nos preguntan si existe algún requisito, como habe5r practicado deporte antes o tener conocimiento de crossfit, nuetra respuesta siempre es la misma: ¡Solo necesitas las ganas!</small>
						</div>
						<div class="col-12 text-center pt-4">
							<a target="_black" class="btn btn-lg btn-pink m-2" :href="data.contact_me"><strong class="text-uppercase">Clase de prueba</strong></a>
							<a target="_black" class="btn-lg btn btn-pink m-2" :href="data.proof_class"><strong class="text-uppercase">Te contactamos</strong></a>
						</div>
					</div>
				</div>
			</div>
			<div v-if="page == 6" class="c-app flex-row align-items-center"> 
				<div class="container">
					<div class="row m-0">
						<div class="col-12 col-sm-12 col-md-4">
							<iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3458.2481028783677!2d-71.26749438488795!3d-29.914758781929695!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x9691ca14917ac111%3A0xcddb2e709cf963ed!2sLos%20N%C3%ADsperos%2043%2C%20La%20Serena%2C%20Coquimbo!5e0!3m2!1ses!2scl!4v1602095631555!5m2!1ses!2scl" width="100%" height="450" frameborder="0" style="border:0;" allowfullscreen="" aria-hidden="false" tabindex="0"></iframe>
						</div>
						<div class="col-12 col-sm-12 col-md-8">
							<div class="row align-items-center h-100">
							<div class="col-12 text-uppercase">
								<h2 class="font-weight-bold text-white pb-4 text-break"><span class="text-pink mr-4">Correo</span><br>{{ data.email }}</h2>
								<h2 class="font-weight-bold text-white pb-4 text-break"><span class="text-pink mr-4">Numero</span><br>{{ data.phone }}</h2>
								<h2 class="font-weight-bold text-white pb-4 text-break"><span class="text-pink mr-4">Ubicación</span><br>{{ data.direction }}</h2>
							</div>
							</div>
						</div>
						<div class="col-12 text-center pt-4">
							<a target="_black" class="btn btn-lg btn-pink m-2" :href="data.contact_me"><strong class="text-uppercase">Clase de prueba</strong></a>
							<a target="_black" class="btn-lg btn btn-pink m-2" :href="data.proof_class"><strong class="text-uppercase">Te contactamos</strong></a>
						</div>
					</div>
				</div>
			</div>
		</div>
		<!-- coach -->
		<div v-if="page == 1" class="container-full" style="background-color: #e6ebf0">
			<div class="row m-0 p-4">
				
				<div class="col-12 text-center pt-2 pb-4">
					<div class="h3 text-body letter-spacing-0 bold text-uppercase"><strong>Conoce a nuestros entrenadores</strong></div>
				</div>
				<div class="col-6">
					<div class="col-12 text-center">
						<img height="250px" src="./assets/images/camila_foto_perfil.png" style="cursor: pointer;">
					</div>
					<div class="col-12  pt-3">
						<div class="h2 text-body letter-spacing-0 text-uppercase text-center"><strong>Camila Contreras</strong></div>
						<h3 class="text-justify"><strong>"</strong>Creo en la importancia de desarrollar una sociedad que valore el bienestar, la vida plena y la felicidad como pilares fundamentales para un bien común<strong>"</strong>.</h3>
					</div>
				</div>
				<div class="col-6">
				
				<div class="col-12 text-center">
					<img height="250px" src="./assets/images/javier_foto_perfil.png" style="cursor: pointer;">
				</div>
				<div class="col-12 pt-3">
					<div class="h2 text-body letter-spacing-0 text-uppercase text-center"><strong>Javier Miranda</strong></div>
					<h3 class="text-justify"><strong>"</strong>Mi mayor motivación es ser testigo de los resultados de las personas con quienes trabajo; acompañarlos en su proceso de desarrollo tanto físico como mental y espiritual<strong>"</strong>.</h3>
				</div>
			</div>

			</div>
		</div>
		<!--crossfit -->
		<div v-if="page == 2" class="container-full">
			<div class="row ml-0 align-items-center" v-bind:style="style_crossfit_1">
				<div class="col-12 pt-4 text-white text-center d-sm-none">
					<div class="font_third_rail display-4 text-white pt-4 mt-4 letter-spacing-0">para <span class="text-dark">cualquier</span> persona</div>
				</div>
				<div class="col-12 pt-4 text-white text-center d-none d-sm-block">
					<div class="font_third_rail display-1 text-white pt-4 mt-4 letter-spacing-0">para <span class="text-dark">cualquier</span> persona</div>
				</div>
				<div class="col-12 text-white text-center">
					<div class="h5 text-white text-uppercase">puede practicarlo cualquier persona esté o no en forma física. De echo, el éxito del crossfit reside en su facilidad para adaptarse a cualquier condición.</div>
				</div>
			</div>
			<div class="row ml-0 align-items-center" v-bind:style="style_crossfit_2">
				<div class="col-12 pt-4 text-white text-center d-sm-none">
					<div class="font_third_rail display-4 text-white pt-4 mt-4 letter-spacing-0">Nivel mas <span class="text-pink">Alta</span></div>
					<div class="h5 text-white text-uppercase">En su nivel más alto de competición encontramos gente exigente que quiere esforzarse al máximo.</div>
				</div>
				<div class="col-12 pt-4 text-white text-center d-none d-sm-block">
					<div class="font_third_rail display-1 text-white pt-4 mt-4 letter-spacing-0">Nivel mas <span class="text-pink">Alta</span></div>
					<div class="h5 text-white text-uppercase">En su nivel más alto de competición encontramos gente exigente que quiere esforzarse al máximo.</div>
				</div>
			</div>
			<div class="row ml-0 align-items-center" v-bind:style="style_crossfit_3">
				<div class="col-12 pt-4 text-white text-center d-sm-none">
					<div class="font_third_rail display-4 text-white pt-4 mt-4 letter-spacing-0">Nivel mas <span class="text-dark">Ligero</span></div>
					<div class="h5 text-white text-uppercase">En un nivel más ligero se encuentra la mayoría de crossfiters en el mundo. <p>Hombres y mujeres de todas las edades que buscan ponerse en forma, estar más ágiles, saludables y conseguir grandes resultados con su cuerpo que se notan enseguida a la visa y en su acticadad diaria.</p></div>
				</div>
				<div class="col-12 pt-4 text-white text-center d-none d-sm-block">
					<div class="font_third_rail display-1 text-white pt-4 mt-4 letter-spacing-0">Nivel mas <span class="text-dark">Ligero</span></div>
					<div class="h5 text-white text-uppercase">En un nivel más ligero se encuentra la mayoría de crossfiters en el mundo. <p>Hombres y mujeres de todas las edades que buscan ponerse en forma, estar más ágiles, saludables y conseguir grandes resultados con su cuerpo que se notan enseguida a la visa y en su acticadad diaria.</p></div>
				</div>
			</div>
		</div>
		<div v-if="page == 3" class="container-full">
			<div class="row m-0 align-items-center" v-bind:style="style_open_box_1">
				<div class="col-12 pt-4 text-white text-center d-sm-none">
					<div class="font_third_rail display-4 text-white pt-4 mt-4 letter-spacing-0">LLega a box y ponte a <span class="text-dark">entrenar</span></div>
					<div class="h5 text-white text-uppercase">El open box solo esta habilitados en las horas indicadas en la pestaña "planes y horarios"</p></div>
				</div>
				<div class="col-12 pt-4 text-white text-center d-none d-sm-block">
					<div class="font_third_rail display-1 text-white pt-4 mt-4 letter-spacing-0">LLega a box y ponte a <span class="text-dark">entrenar</span></div>
					<div class="h4 text-white text-uppercase">El open box solo esta habilitados en las horas indicadas en la pestaña "planes y horarios"</p></div>
				</div>
			</div>
		</div>
		<!-- instagram -->
		<div class="container-full" style="background-color: #f4f5f6">
			<div class="row m-0 p-4">
				<div class="col-12 text-center pt-2 pb-4">
					<div class="h3 text-body letter-spacing-0 bold text-uppercase"><strong>sigue a nuestra comunidad</strong></div>
				</div>
				<div class="container-sm">
					<div class="row m-0">
						<div class="col-6 col-md-4 text-center">
							<a :href="data.instagram" target="_black" ><img src="./assets/images/insta/IMG_1.jpg" class="c-pointer w-100"></a>
						</div>
						<div class="col-6 col-md-4 text-center">
							<a :href="data.instagram" target="_black" ><img src="./assets/images/insta/IMG_2.jpg" class="c-pointer w-100"></a>
						</div>
						<div class="col-6 col-md-4 text-center">
							<a :href="data.instagram" target="_black" ><img src="./assets/images/insta/IMG_3.jpg" class="c-pointer w-100"></a>
						</div>
						<div class="col-6 col-md-4 text-center">
							<a :href="data.instagram" target="_black" ><img src="./assets/images/insta/IMG_4.jpg" class="c-pointer w-100"></a>
						</div>
						<div class="col-6 col-md-4 text-center">
							<a :href="data.instagram" target="_black" ><img src="./assets/images/insta/IMG_5.jpg" class="c-pointer w-100"></a>
						</div>
						<div class="col-6 col-md-4 text-center">
							<a :href="data.instagram" target="_black" ><img src="./assets/images/insta/IMG_6.jpg" class="c-pointer w-100"></a>
						</div>
					</div>
				</div>
				<div class="col-12 text-white text-center">	
					<div class="menu_font_built_bold display-1 text-white pt-4 mt-4 letter-spacing-0"  style="text-shadow: 0.05em 2.1px 0.03em #09152bcc;">Prove <span class="text-pink">your</span> fitness</div>
				</div>
			</div>
		</div>
	</div>

	<footer class="footer mt-auto py-3 bg-pink">
		<div class="container text-center">
			<a :href="data.maps" class="btn text-white pl-2" target="_black" ><i class="fas fa-map-marker-alt pr-2" style="font-size: 25px;"></i><span style="font-size: 15px;">{{ data.direction }}</span></a>
			<a :href="data.facebook" class="btn text-white pl-2" target="_black" ><i class="fab fa-facebook" style="font-size: 25px;"></i></a>
			<a :href="data.whatsapp" class="btn text-white pl-2" target="_black" ><i class="fab fa-whatsapp" style="font-size: 25px;"></i></a>
			<a :href="data.instagram" class="btn text-white pl-2" target="_black" ><i class="fab fa-instagram" style="font-size: 25px;"></i></a>
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
					name: 'Dharma Training',
					direction: 'Los nísperos 43, La Serena',
					email: 'contacto.dharma.ls@gmail.com',
					maps: 'https://goo.gl/maps/dryW6WmTtVmJAUn56',
					phone: '+569-75504789',
					whatsapp: 'https://wa.me/+56975504789',
					facebook: 'https://www.facebook.com/dharmatraining',
					instagram: 'https://www.instagram.com/dharma_training/',
					contact_me: 'https://docs.google.com/forms/d/e/1FAIpQLSfetT2fpC36yNuKZtVmeBbGb6OxTG_r1Hs3NZ2K5O3OfFv0sA/viewform',
					proof_class: 'https://docs.google.com/forms/d/1X6rsj_TXxmsiK8QDu9Acr9mW4VAp-ILdAmbS6BPb9Hg/viewform?edit_requested=true',
					text_inicio: 'Texto 1: vision. breve descripcón del servicio haiendo hincapie en idea de desciplina inegral, quizás desmitificar idea de crossfit como "deporte rudo-militar"',
					text_crossfit: 'El crossfit es una actividad física de alto rendimiento que tiene como objetivo desarrollar diversas capacidades corporales.',
					text_open_box: 'Horas en las que el box estará abierto a los crossfiters. Estas horas irán dedicadas para practicar movimientos o mejorar técnicas.',
				},
				title_page: 'Dharma training',
				variant: 'dark',
				style_object: {
					'background-size': 'cover',
					'background-image': `url(${require('./assets/images/enmascarar_grupo_1.png')})`
				},
				style_object_2: {
					'background-size': 'cover',
					'background-image': `url(${require('./assets/images/enmascarar_grupo_2.png')})`
				},
				style_crossfit_1: {
					'background-size': 'cover',
					'background-image': `url(${require('./assets/images/enmascarar_grupo_4.png')})`,
					'min-height': '80vh'
				},
				style_crossfit_2: {
					'background-size': 'cover',
					'background-image': `url(${require('./assets/images/enmascarar_grupo_5.png')})`,
					'min-height': '100vh'
				},
				style_crossfit_3: {
					'background-size': 'cover',
					'background-image': `url(${require('./assets/images/enmascarar_grupo_6.png')})`,
					'min-height': '100vh'
				},
				style_open_box_1: {
					'background-size': 'cover',
					'background-image': `url(${require('./assets/images/enmascarar_grupo_8.png')})`,
					'min-height': '100vh'
				},
				slide: 0,
        		sliding: null,
				page: 0,
				hide:false,
			}
		},

		methods: {
			onOpen(id_popover) {
                console.log()
                this.$root.$emit('bv::hide::popover')
                this.$root.$emit('bv::show::popover',id_popover);
            },
            onClose(id_popover) {
                this.$root.$emit('bv::hide::popover', id_popover)
            },

            hide_modal(id) {
                this.$bvModal.hide(id);
            },

            show_modal(id) {
                this.$bvModal.show(id);
            },

			onSlideStart(slide) {
        		this.sliding = true
		    },
	    	onSlideEnd(slide) {
	        	this.sliding = false
	      	},
			change_page(number) {
				//this.v-b-toggle="['my-collapse1', 'my-collapse2']"
				
				this.hide = false;
				this.page = number;

				if (this.page == 1) {
					this.style_object_2['background-image'] = `url(${require('./assets/images/enmascarar_grupo_10.png')})`;
				}

				if (this.page == 2) {
					this.style_object_2['background-image'] = `url(${require('./assets/images/enmascarar_grupo_3.png')})`;
				}

				if (this.page == 3) {
					this.style_object_2['background-image'] = `url(${require('./assets/images/enmascarar_grupo_7.png')})`;
				}

				if (this.page == 4) {
					this.style_object_2['background-image'] = `url(${require('./assets/images/enmascarar_grupo_9.png')})`;
				}

				if (this.page == 5) {
					this.style_object_2['background-image'] = `url(${require('./assets/images/enmascarar_grupo_2.png')})`;
				}

				if (this.page == 6) {
					this.style_object_2['background-image'] = `url(${require('./assets/images/enmascarar_grupo_11.png')})`;
				}
			}
		}
	}
</script>