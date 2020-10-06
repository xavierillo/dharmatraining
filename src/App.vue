<template>
<div id="app">
 	        <header class="fixed-top page-header">
            <div class="container-fluid navbar navbar-dark bg-dark navbar-expand-md">
                <div class="row  w-100">
                    <div class="col-12 d-md-none d-sm-block text-white menu_font_built_bold letter-spacing-1 text-center" style="font-size: 12px;">
                        <i class="fab fa-facebook"></i>
                        <i class="fab fa-whatsapp pl-2"></i>
                        <i class="fab fa-instagram pl-2"></i>
                        <i class="fas fa-map-marker-alt pl-2"></i> Los nísperos 43, La Serena
                    </div>
                    <div class="col-2 text-center">
                        <img class="navbar-brand" src="./assets/images/dharma_100px.png">
                    </div>
                    <div class="col-8 mt-3">
                        <div class="collapse navbar-collapse justify-content-lg-center">
                            <ul class="navbar-nav menu_font_built_bold letter-spacing-2">
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
                    <div class="col-2 ml-auto ml-0">
                        <div class="collapse navbar-collapse row text-white text-white menu_font_built_bold letter-spacing-1 text-center mt-2">
                            <div class="col-12" style="font-size: 16px;">
                                <i class="fas fa-map-marker-alt  pr-2"></i> <span style="font-size: 14px;">Los nísperos 43, La Serena</span>
                            </div>
                            <div class="col-12">
                                <i class="fab fa-facebook"></i>
                                <i class="fab fa-whatsapp pl-2"></i>
                                <i class="fab fa-instagram pl-2"></i>
                            </div>
                        </div>
                        <div class="text-right h-100 d-flex" style="justify-content: center;  align-items: center;">
                            <button class="navbar-toggler" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
                                <span class="navbar-toggler-icon"></span>
                            </button>
                        </div>
                    </div>
                </div>
            </div>
  
        </header>
        asdasdasd
        asdasd
</div>
</template>

<script>
export default {
  name: 'app',
  data () {
	return {
	  msg: 'DHARMAAAA'
	}
  }
}
</script>

<style lang="scss">
  #app {
	font-family: 'Avenir', Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
	margin-top: 60px;
  }

  h1, h2 {
	font-weight: normal;
  }

  ul {
	list-style-type: none;
	padding: 0;
  }

  li {
	display: inline-block;
	margin: 0 10px;
  }

  a {
	color: #42b983;
  }
</style>
