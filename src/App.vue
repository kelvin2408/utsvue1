<template>
<html>
  <head>
  <link rel="stylesheet" src="https://stackpath.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css" />
</head>
<body>
    <div>
      <nav class="navbar navbar-expand">
        <img src="/pictures/logo1.png" width="270px" height="90x" class="navbar-brand p-2"/>
            <div class="collapse navbar-collapse" id="menu-raja">
      <ul class="navbar-nav mr-auto mt-2 mt-lg-0 kiri">
        <li class="nav-item active">
          <a class="nav-link" href="#">Home</a>
        </li>
        <li class="nav-item active">
          <a class="nav-link" href="#">Shop</a>
        </li>
        <li class="nav-item active">
          <a class="nav-link" href="#">Features</a>
        </li>
        <li class="nav-item active">
          <a class="nav-link" href="#">Pages</a>
        </li>
        <li class="nav-item active">
          <a class="nav-link" href="#">Blog</a>
        </li>
      </ul>
    </div>
        <div class="collapse navbar-collapse">
          <ul class="nav navbar-nav ml-auto">
          <li class="nav-item mx-3  ">
              <a class="nav-link" href=""><img src="/pictures/user.svg" width="30px" height="30px"/></a>
          </li>
          <li class="nav-item mx-2">
              <a class="nav-link" href=""><img src="/pictures/shopping-cart.svg" width="30px" height="30px"/></a>
          </li>
          </ul>
        </div>
        </nav>
    <b-carousel
      id="carousel-1"
      v-model="slide"
      :interval="4000"
      controls
      indicators
      background="#ababab"
      img-width="1024"
      img-height="480"
      style="text-shadow: 1px 1px 2px #333;"
      @sliding-start="onSlideStart"
      @sliding-end="onSlideEnd"
    >
      <!-- Text slides with image -->
      <b-carousel-slide
        caption="Happy Fashion"
        text="Nulla vitae elit libero, a pharetra augue mollis interdum."
        img-src="/pictures/slider1.jpg"
      ></b-carousel-slide>

      <b-carousel-slide
        caption="Your Fashion Your Future"
        text="Nulla vitae elit libero, a pharetra augue mollis interdum."
        img-src="/pictures/slider2.jpg"
      ></b-carousel-slide>

      <b-carousel-slide
        caption="Imagine Style"
        text="Nulla vitae elit libero, a pharetra augue mollis interdum."
        img-src="/pictures/slider3.jpg"
      ></b-carousel-slide>
    </b-carousel>
    </div>
<div id="category-sect">
    <h4 class="font-weight-bold pt-5 text-center"> Shop By Category </h4>
      <section id="tabs" class="project-tab">
        <div class="container-fluid">
            <div class="row justify-content-center">
                <div class="col-md-12">
                    <b-tabs content-class="mt-3" fill>
                    <b-tab title="Jacket" active>
                    <ul class="container mt-4">
                          <div class="row">
                        <div v-for="(jacket, index) in Jacket" :key="index" class="my-3 mr-2 text-center">
                          <div class="product-image">
                            <img class="img-responsive h-75 w-120 p-2" src="/pictures/jacket2.jpg" />
                            </div>
                          <div class="product-details">
                            <h6 class="display-6 mt-3">{{ jacket.name }}</h6>
                            <h6 class="display-6 text-muted">Rp.{{ jacket.price }}</h6>
                          </div>
                        </div>
                    </div>
                    </ul>
                    </b-tab>
                    <b-tab title="T-Shirts">
                      <ul class="container mt-4">
                          <div class="row">
                        <div v-for="(tshirt, index) in Tshirts" :key="index" class="my-3 mr-2 text-center">
                          <div class="product-image">
                            <img class="img-responsive h-75 w-120 p-2" src="/pictures/jacket.webp" />
                            </div>
                          <div class="product-details">
                            <h6 class="display-6 mt-3">{{ tshirt.name }}</h6>
                            <h6 class="display-6 text-muted">Rp.{{ tshirt.price }}</h6>
                          </div>
                        </div>
                    </div>
                    </ul>
                      </b-tab>
                    <b-tab title="Sneakers">
                      <ul class="container mt-4">
                          <div class="row">
                        <div v-for="(sneaker, index) in Sneakers" :key="index" class="my-3 mr-2 text-center">
                          <div class="product-image">
                            <img class="img-responsive h-75 w-100 p-2" src="/pictures/sneaker1.jpg" />
                            </div>
                          <div class="product-details">
                            <h6 class="display-6 mt-3">{{ sneaker.name }}</h6>
                            <h6 class="display-6 text-muted">Rp.{{ sneaker.price }}</h6>
                          </div>
                        </div>
                    </div>
                    </ul>
                    </b-tab>
                  </b-tabs>

                    </div>
                </div>
            </div>
            </section>
        </div>
</body>
<footer class="page-footer blue pt-5 mt-5">
<div class="container-fluid text-center text-md-left">
      <div class="row">
        <div class="col-md-3 mt-md-0 mt-3">
          <img class="px-5" img src="/pictures/logo1.png" width="350px" height="90x" />
        </div>

        <hr class="clearfix w-100 d-md-none pb-3">
        <div class="col-md-3 mb-md-0 mb-3">

          <h5 class="text-uppercase"> OUTLET LAIN</h5>

        </div>
        <div class="col-md-3 mb-md-0 mb-3">

          <h5 class="text-uppercase">TENTANG KAMi</h5>

        </div>

        <div class="col-md-3 mb-md-0 mb-3">

          <h5 class="text-uppercase">CONTACT US</h5>

        </div>

      </div>

    </div>

    <div class="footer-copyright text-right py-3 mr-3">© 2020 Copyright: FLUVIN
    </div>
  </footer>

</html>
  <!-- <div id="app">
    <h1 v-for="(shirt, index) in shirts" :key="index">{{ shirt.name }}</h1>
    <h1 v-for="(tshirt, index) in tshirts" :key="index">{{ tshirt.price }}</h1>
    </div> -->
</template>

<script>
import axios from 'axios'
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'

export default {
  name: 'App',
  data () {
    return {
      Jacket: [],
      Tshirts: [],
      Sneakers: []
    }
  },
  async created () {
    const baseURI = 'https://my-json-server.typicode.com/kelvin2408/utsvue/db'
    axios.get(baseURI)
      .then((result) => {
        this.Jacket = result.data.Jacket
        this.Tshirts = result.data.Tshirts
        this.Sneakers = result.data.Sneakers
      })
  }
}

</script>

<style>
@media (min-width: 992px) {
      .navbar-brand {
        position: absolute;
        left: 50%;
        transform: translateX(-50%);
        font-family: "Poppins",sans-serif;
        color: #23232c;
        letter-spacing: 2.5px;
      }
    }
    .kiri {
      margin-left: 40px;
    }
    .kanan {
      margin-right: 40px;
    }
    @media (max-width: 991px) {
      .navbar-brand {
        height: 0;
        margin-top: -90px;
        left: 10%;
      }
      .navbar-nav{
        margin-top: 10px;
        margin-left: 40%;
      }
    }
    .raja-nav{
      background-color: white;
      padding-top: 25px;
      padding-bottom: 25px;
      font-family: Laila, serif;
      font-size: 1.2rem;
      color: #23232c;
      font-weight: 600;
      text-transform: uppercase;
    }
    .navbar-nav > li > a:hover {
      /*  */
    }
    .navbar-toggler-icon {
      background-image: url("data:image/svg+xml;charset=utf8,%3Csvg viewBox='0 0 32 32' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath stroke='rgba(34, 155, 168, 1)' stroke-width='2' stroke-linecap='round' stroke-miterlimit='10' d='M4 8h24M4 16h24M4 24h24'/%3E%3C/svg%3E");
    }
    .navbar-nav > li{
      margin-right: 20px;
    }
    .navbar-nav > li > a{
      color: #23232c;
      font-size: 14px;
      font-family: "Poppins",sans-serif;
    }
    .navbar-toggler {
      margin-left: 90%;
    }

#my-jumbotron {
    background-size: cover;
    overflow: hidden;
}
#jumbo-text-contain {
    color: black;
    min-height: 400px;
}
#jumbotron-btn {
    font-size: 20px;
    border: 3px solid ;
    border-radius: 0;
    transition: 0.3s;
}
#jumbotron-btn:hover {
    color:white ;
    border: 1px solid white;
}
#products-container li{
    list-style-type: none;
    height: 250px;
}
.product-image {
    background: #f4f4ef;
    width: 250px;
    height: 275px;
}
.project-tab {
    padding: 10%;
    margin-top: -8%;
}
.project-tab #tabs{
    background: #007b5e;
    color: #eee;
}
.project-tab #tabs h6.section-title{
    color: #eee;
}
.project-tab #tabs .nav-tabs .nav-item.show .nav-link, .nav-tabs .nav-link.active {
    color: #20232a;
    background-color: transparent;
    border-color: transparent transparent #f3f3f3;
    border-bottom: 3px solid !important;
    font-size: 16px;
    font-weight: bold;
}
.project-tab .nav-link {
    border: 1px solid transparent;
    border-top-left-radius: .25rem;
    border-top-right-radius: .25rem;
    color: #acbebe;
    font-size: 16px;
    font-weight: 600;
}
.project-tab .nav-link:hover {
    border: none;
}
.project-tab thead{
    background: #f3f3f3;
    color: #333;
}
.project-tab a{
    text-decoration: none;
    color: #333;
    font-weight: 600;
}
.page-footer {
    color: white;
    background: #20232a;
}
</style>
