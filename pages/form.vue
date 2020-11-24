<template>
  <div class="d-flex flex-column">
    <div id="app" class=" container-fluid">
      <header>
        <nav class="navbar navbar-expand-sm navbar-light bg-white">
          <a class="navbar-brand mx-auto ml-md-1" href="#">
            <img src="/images/brand.svg" class="brand-logo-cdmx">
          </a>
          <div id="navbarSupportedContent ml-3" class="collapse navbar-collapse bar">
            <div class="linea auto-hide pl-2" />
            <div class="jeader-title auto-hide gotham fw-bold fs-9">
              Plan Gradual hacia la Nueva Normalidad
            </div>
          </div>
          <ul class="navbar-nav mx-auto ml-md-auto my-2 my-md-0">
            <li class="nav-item">
              <a class="nav-link text-center" href="#background-image">
                <img src="/images/btn-llave-sm.png" title="Iniciar sesión con Llave CDMX">
              </a>
              <div class="tx-crea-cuenta">
                ¿Aún no tienes cuenta? <a href="#" target="_blank">Crea una</a><p />
              </div>
            </li>
          </ul>
        </nav>
      </header>
    </div>

    <div class="container-fluid flex-fill snow-back">
      <div v-if="success" class="alert alert-success text-center fs-24 fw-bold" role="alert">
        Registro guardado exitosamente
      </div>

      <div class="row green-cover pt-3">
        <h2 class="col-12 mx-auto text-center metropolis fw-bold fs-36 white">
          Bienvenido al registro de apertura
        </h2>
        <h3 class="col-12 mx-auto text-center metropolis fw-medium fs-28 white">
          Para poner en marcha la Nueva Normalidad
        </h3>
      </div>
      <div class="white-container mx-auto mb-0 py-3 px-0">
        <h4 class="col-12 metropolis fw-bold fs-24 mt-lg-5 mt-3 mx-2">
          Para el Gobierno de la Ciudad de México los ciudadanos son lo más importante
        </h4>
        <p class="col-12 fs-20 fw-regular mx-2">
          Desde el inicio de la propagación del virus SARS-COV2, el Gobierno de la Ciudad de México ha implementado una serie de acciones dirigidas a prevenir, evitar su contagio y propagación, es así que a través del sistema centralizado de información, para el seguimiento epidemiológico se realiza la identificación, seguimiento y rastreo de casos positivos y sospechosos de posibles contagios así como su red de contactos o ubicación de zonas de contagio minimizando los riesgos de contagios de COVID-19 entre la población.
        </p>

        <div class="col-12 mintcream-back px-0 mx-0 pt-3 pb-5">
          <form method="POST" class="mx-auto" @submit.prevent="showSuccessMessage">
            <h4 class="col-12 col-sm-10 offset-sm-1 col-md-8 col-lg-10 offset-lg-1 metropolis fw-bold fs-24 mt-4 mt-lg-5 mx-auto ml-lg-1">
              REGISTRA TU ASISTENCIA
            </h4>
            <div class="mx-auto ml-lg-1 col-12 col-sm-10 offset-sm-1 col-md-8 col-lg-6 col-xl-5 my-3 align-items-center">
              <label for="telefono" class="fs-14 firefly fw-regular">Introduce tu número de teléfono a 10 dígitos</label>
              <input
                id="telefono"
                type="text"
                name="telefono"
                value=""
                class="form-control number required "
                maxlength="10"
                placeholder="55 5555 5555"
              >

              <span id="error-tel" class="error_form" />
            </div>
            <div class="d-flex mx-auto ml-lg-1 col-12 col-sm-10 offset-sm-1 col-md-8 col-lg-6 col-xl-5">
              <button type="submit" class="mx-auto ml-sm-0 btn-01 btn-01x fs-14">
                Enviar registro
              </button>
            </div>
          </form>
        </div>

        <h4 class="col-12 metropolis fw-bold fs-24 mt-4 mt-lg-5 mx-2">
          Información del registro
        </h4>
        <div class="col d-flex flex-wrap datos-negocio">
          <div class="col-12 col-lg-6">
            <span>Fecha de registro:</span> {{ today }}
          </div>
          <div class="col-12 col-lg-6">
            <span>Folio de registro:</span> PGHNN/111111/111/0161111193
          </div>
          <div class="col-12 col-lg-6">
            <span>Actividad económica:</span> Comercio al por menor de ropa, excepto de bebé y lencería
          </div>
          <div class="col-12 col-lg-6">
            <span>Color del semáforo:</span> Naranja
          </div>

          <h4 class="col-12 metropolis fw-bold fs-24 mt-lg-5">
            Matriz
          </h4>
          <div class="col-12 col-lg-6">
            <span>Nombre:</span> Wharever SA de CV.
          </div>
          <div class="col-12 col-lg-6">
            <span>Teléfono:</span> 55 3322 2222
          </div>
          <div class="col-12 col-lg-6">
            <span>Domicilio:</span> Av. Miguel Angel de Quevedo #227, Colonia Romero de Terreros, Alcaldía Coyoacán
          </div>

          <div class="col-12 d-flex justify-content-center justify-content-md-start">
            <a href="" target="_blank" class="shamrock fs-16">Aviso de privacidad simplificado</a>
          </div>
        </div>
      </div>
    </div>
    <div id="modal-logo" class="modal fade" tabindex="-1" role="dialog">
      <div class="modal-dialog modal-dialog-centered" role="document">
        <div class="modal-content">
          <div class="modal-body">
            <div class="alert alert-warning" role="alert" style="display: none;">
              Tu sesión ha caducado. Debes iniciar sesion de nuevo.
            </div>
          </div>
          <div class="modal-footer">
            <button id="relogi" type="button" class="btn btn-cdmx">
              Iniciar sesión
            </button>
          </div>
        </div>
      </div>
    </div>

    <footer class="d-flex align-items-center flex-wrap flex-lg-nowrap">
      <div class="col-12 col-lg-4 text-center">
        <img class="img-footer brand-logo-cdmx pi-footer" src="/images/adip-footer.svg" alt="">
      </div>
      <div class="col-12 col-lg-4 text-center text-lg-left white">
        <p class="label-footer">
          Plan Gradual hacia la Nueva Normalidad
        </p>
        <p class="label-footer">
          <strong>Diseñado  y operado por...</strong>
        </p>
      </div>
      <div class="col-12 col-lg-3 text-center text-lg-right">
        <p class="label-footer">
          <a href="" target="_blank" class="white">Aviso de privacidad</a>
        </p>
        <p class="label-footer">
          <a href="" target="_blank" class="white">Términos y condiciones</a>
        </p>
      </div>
      <div id="footer-mark" />
    </footer>
  </div>
</template>

<script>
import '../assets/app.css'
export default {
  data () {
    const date = new Date()
    return {
      success: false,
      today: `${date.getFullYear()}-${date.getMonth()}-${date.getDate()}`
    }
  },
  methods: {
    showSuccessMessage () {
      this.success = true

      window.scrollTo({ top: 0, behavior: 'smooth' })
    }
  }
}
</script>
