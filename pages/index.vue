<template>
  <div id="content">
    <div class="banner">
      <div class="non-mobile hidden-md-and-down">
        <v-layout row wrap>
          <v-flex md5>
              <v-container>
                  <div class="img">
                    <img src="https://livedemo00.template-help.com/wt_59166_v1/images/home-1-800x659.png" alt=""
                    style="margin-top: 50px">
                  </div>
              </v-container>

          </v-flex>
          <v-flex md7>
              <v-container>
                <div class="banner-text">
                  <h1><strong class="text-white">Software</strong> Silo</h1>
                  <div class="wrap">
                    <p class="big">INNOVATIVE SOLUTIONS</p>
                    <p class="text-white medium">Innovative solutions delivering a product, which includes tomorrow’s technology – already today!</p>
                  </div>
                </div>
              </v-container>

          </v-flex>
            <v-container>
              <div class="typing">
                <vue-typer class="vue-typer" :text='["Create awesomeness now!", "with Software Silo"]'
                erase-style='backspace'  :erase-on-complete='true'  caret-animation='expand'>
                </vue-typer>
              </div>
            </v-container>
        </v-layout>
      </div>

      <div class="mobile hidden-md-and-up">
        <v-layout column wrap>
          <v-flex md7>
            <v-container>
              <div class="banner-text">
                <h1><strong class="text-white">Software</strong> Silo</h1>
                <div class="wrap">
                  <p class="big">INNOVATIVE SOLUTIONS</p>
                  <p class="text-white medium">Innovative solutions delivering a product, which includes tomorrow’s technology – already today!</p>
                </div>
              </div>
            </v-container>
          </v-flex>

          <v-flex md5>
            <v-container>
              <div class="img">
                <img src="https://livedemo00.template-help.com/wt_59166_v1/images/home-1-800x659.png" alt="">
              </div>
            </v-container>
          </v-flex>

        </v-layout>
      </div>

    </div>

      <div class="services">
      <v-container>
        <v-layout align-center justify-center row fill-height>
          <h2 class="border-bottom">Why Choose Us?</h2>
        </v-layout>
      <v-layout row wrap>
          <v-flex md4>
            <div class="service">
              <h4>MOBILE RESPONSIVE</h4>
              <p>Fusce sed tellus quam. Integer posuere ipsum ac mauris pharetra, pulvinar pharetra neque porttitor. Sed lectus eros,
                 porttitor non libero sit amet, scelerisque semper augue. Mauris scelerisque vestibulum ligula vel posuere. </p>
             </div>
            </v-flex>
            <v-flex md4>
              <div class="service">
                <h4>TOP TECHNOLOGY STACK</h4>
                <p>Fusce sed tellus quam. Integer posuere ipsum ac mauris pharetra, pulvinar pharetra neque porttitor. Sed lectus eros,
                   porttitor non libero sit amet, scelerisque semper augue. Mauris scelerisque vestibulum ligula vel posuere. </p>
              </div>
            </v-flex>
            <v-flex md4>
              <div class="service">
                <h4>QUALITY</h4>
                <p>Fusce sed tellus quam. Integer posuere ipsum ac mauris pharetra, pulvinar pharetra neque porttitor. Sed lectus eros,
                   porttitor non libero sit amet, scelerisque semper augue. Mauris scelerisque vestibulum ligula vel posuere. </p>
              </div>
          </v-flex>
      </v-layout>
    </v-container>
    </div>

    <div class="teams">
      <v-container>
        <v-layout align-center justify-center row fill-height>
          <h2 class="border-bottom border-black">Our Engineers</h2>
        </v-layout>
        <v-layout row wrap>
          <v-flex md6>
            <div class="team">
              <h3>Adis Azhar</h3>
              <p>Quisque ut velit rhoncus, tempus metus in, lobortis lacus. Nam a nisi sapien. Mauris malesuada dolor at po
                rta feugiat. Curabitur blandit, odio at tempor tempor, nibh justo gravida mauris, non ornare tellus mauris et lec
                us. Proin imperdiet varius dolor. Vivamus ut elit dui. Pellentesque a lectus tempus, aliquam dolor ut, facilisis velit.</p>
            </div>
          </v-flex>
          <v-flex md6>
            <div class="team">
              <h3>Andika Andra</h3>
              <p>Quisque ut velit rhoncus, tempus metus in, lobortis lacus. Nam a nisi sapien. Mauris malesuada dolor at porta feugiat.
                Curabitur blandit, odio at tempor tempor, nibh justo gravida mauris, non ornare tellus mauris et lectus. Proin imperdiet
                 varius dolor. Vivamus ut elit dui. Pellentesque a lectus tempus, aliquam dolor ut, facilisis velit.</p>
            </div>
          </v-flex>
        </v-layout>
      </v-container>
    </div>

    <div class="technologies">
      <!-- <v-container> -->
      <v-layout row wrap>
        <v-flex md3>
        <div class="tech">
          <v-tooltip bottom>
            <img slot="activator" src="https://upload.wikimedia.org/wikipedia/commons/3/3d/LaravelLogo.png" alt="">
             <span>Laravel</span>
          </v-tooltip>
        </div>
      </v-flex>

      <v-flex md3>
      <div class="tech">
        <v-tooltip bottom>
          <img slot="activator" src="https://sailsjs.com/images/logos/sails-logo_ltBg_ltBlue.png" alt="" style="width: 150px">
          <span>Sails Js</span>
        </v-tooltip>
      </div>
    </v-flex>

    <v-flex md3>
      <div class="tech">
        <v-tooltip bottom>
          <img slot="activator" src="https://cdn-images-1.medium.com/max/600/1*Z3QcBB__mvWCqood2fbiBQ.png" alt="" style="width: 150px">
          <span>Nuxt Js</span>
        </v-tooltip>
      </div>
    </v-flex>

    <v-flex md3>
      <div class="tech">
        <v-tooltip bottom>
        <img slot="activator" src="https://dwglogo.com/wp-content/uploads/2017/12/1100px_Redis_Logo_01.png" alt="" style="width: 150px; margin-top: -20px;">
        <span>Redis</span>
        </v-tooltip>
      </div>
    </v-flex>

    </v-layout>
  <!-- </v-container> -->
    </div>

  </div>

</template>

<script>

</script>

<style>
  .banner{
    background-color: #3fc7c3;
    min-height: 885px;
  }

  .banner h1 {
    font-size: 48px;
    color: black !important;
  }

  .banner-text{
    margin-top: 90px;
  }

  p.big {
    font-size: 46px;
    font-weight: lighter;
  }

  p.medium {
    font-size: 40px;
    font-weight: lighter;
  }

  .text-white{
    color: white;
  }

  .service{
    text-align: center;
    padding: 10px;
  }

  .service:hover{
    border-bottom: solid 3px white;
    cursor: pointer;
  }

  .services {
    background-color: #282b2d;
    color: white;
  }

  .teams {
    background-color: #ffffff;
  }

  .team {
    text-align: center;
    padding: 10px;
  }

  .team:hover {
    border-bottom: solid 3px black;
    cursor: pointer;
  }


  .vue-typer {
    font-size: 40px;
  }
  .vue-typer .custom.char.typed {
    color: #ffffff !important;
  }
  .vue-typer .custom.char.selected {
    color: #E91E63;
  }

  .vue-typer .custom.caret {
    animation: rocking 1s ease-in-out 0s infinite;
    margin: 0 !important;
  }

  .typing {
    margin-left: 100px;
  }

  .tech {
    text-align: center;
    padding: 10px;
  }

  .tech img {
    width: 100px;
    opacity: 0.5;
  }

  .tech img:hover {
    opacity: 1;
    cursor: pointer;
  }

  .technologies {
    padding-top: 15px;
  }

  .mobile .banner-text{
    padding-left: 10px;
    padding-right: 10px;
  }

  .mobile .banner-text p.medium {
    font-size: 22px !important;
  }
  .mobile .banner-text p.big {
    font-size: 32px !important;
  }

  .mobile .banner-text h1 {
    font-size: 38px !important;
  }

  .mobile .img img {
    width: 500px;
    margin-left: -80px;
  }

  .border-bottom {
    border-bottom: 1px solid;
  }

  .border-white {
    border-color: white;
  }

  .border-black {
    border-color: black;
  }


</style>
