<template>
    <div>
      <section id="topbar" class="d-flex align-items-center">
      <div class="container d-flex justify-content-center justify-content-md-between">
      <div class="contact-info d-flex align-items-center">       
        <i class="bi bi-person-circle d-flex align-items-center ms-4"><span>{{this.nombreUsuario}}&nbsp;{{this.nombreApellido}}</span></i>
      </div>
      <div class="social-links d-none d-md-flex align-items-center">
        <a href="#" class="twitter">  <i class="bi bi-twitter"></i></a>
        <a href="#" class="facebook"> <i class="bi bi-facebook"></i></a>
        <a href="#" class="instagram"><i class="bi bi-instagram"></i></a>
        <a href="#" class="linkedin"> <i class="bi bi-linkedin"></i></a>
      </div>
      <b-button @click="cerrarSesion()" variant="danger">Cerrar Sesión &nbsp;&nbsp; <i class="bi bi-box-arrow-right"></i></b-button>
    </div>
  </section>

  <!-- ======= Header ======= -->
  <header id="header" class="d-flex align-items-center">
    <div class="container d-flex align-items-center justify-content-between">

      <h1 class="logo"><a href="./home">MI<span>$</span> FINANZA<span>$</span></a></h1>
      <!-- Uncomment below if you prefer to use an image logo -->
      <!-- <a href="index.html" class="logo"><img src="@/assets/img/logo.png" alt=""></a>-->

      <nav id="navbar" class="navbar">
        <ul>
          <li><a :class="this.clase"  href="./home">Home</a></li>
          <li><a :class="this.clase1" href="./ingresos">Ingresos</a></li>
          <li><a :class="this.clase2" href="./egresos">Egresos</a></li>
          <li><a :class="this.clase3" href="./consolidado">Consolidado</a></li>
          <!-- <li class="dropdown"><a href="#"><span>Drop Down</span> <i class="bi bi-chevron-down"></i></a>
            <ul>
              <li><a href="#">Drop Down 1</a></li>
              <li class="dropdown"><a href="#"><span>Deep Drop Down</span> <i class="bi bi-chevron-right"></i></a>
                <ul>
                  <li><a href="#">Deep Drop Down 1</a></li>
                  <li><a href="#">Deep Drop Down 2</a></li>
                  <li><a href="#">Deep Drop Down 3</a></li>
                  <li><a href="#">Deep Drop Down 4</a></li>
                  <li><a href="#">Deep Drop Down 5</a></li>
                </ul>
              </li>
              <li><a href="#">Drop Down 2</a></li>
              <li><a href="#">Drop Down 3</a></li>
              <li><a href="#">Drop Down 4</a></li>
            </ul>
          </li> -->
          <!-- <li><a class="nav-link scrollto" href="#contact">Contact</a></li> -->
        </ul>
        <span class="btn_menu">
            <i class="bi bi-list mobile-nav-toggle"></i>
        </span>
        </nav><!-- .navbar -->

    </div>
  </header><!-- End Header -->
    </div>
</template>

<script>

</script>
<script>

export default{
  data(){
    return{
    }
  },
  components:{
  },
 

  beforeCreate(){
    var auth = window.localStorage.getItem('AUTH');
    var dataName = window.localStorage.getItem('NOMBRE');
    var dataLastName = window.localStorage.getItem('APELLIDO');
    this.nombreUsuario = dataName;
    this.nombreApellido = dataLastName;

     if(this.$route.name == "Home"){
      this.clase="nav-link scrollto active"
      this.clase1="nav-link scrollto"
      this.clase2="nav-link scrollto"
      this.clase3="nav-link scrollto"
    }
    if(this.$route.name == "Ingresos"){
      this.clase="nav-link scrollto"
      this.clase1="nav-link scrollto active"
      this.clase2="nav-link scrollto"
      this.clase3="nav-link scrollto"
    }
    if(this.$route.name == "Egresos"){
      this.clase="nav-link scrollto"
      this.clase1="nav-link scrollto"
      this.clase2="nav-link scrollto active"
      this.clase3="nav-link scrollto"
    }
    if(this.$route.name == "Consolidado"){
      this.clase="nav-link scrollto"
      this.clase1="nav-link scrollto"
      this.clase2="nav-link scrollto"
      this.clase3="nav-link scrollto active"
    }
    if(auth !== 'ok'){
      this.$router.push({path: '/Login'});
    }
    
  },

  methods:{
    return:{
      
    },
    cerrarSesion(){
      window.localStorage.removeItem('AUTH');
      window.localStorage.removeItem('NOMBRE');
      window.localStorage.removeItem('APELLIDO');
      this.$router.push({path: '/Login'})
    },
  },
  
}
</script>
