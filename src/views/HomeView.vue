<script lang>
import Sphere from '../components/Sphere.vue'
import LoadingScreen from "../components/LoadingScreen.vue"

export default{
  props:{
    sideNav: Array
  },
  components: {
    Sphere,
    LoadingScreen,
  },
  data(){
    return {
      isLoading: true,
    }
  },
  mounted() {
    document.querySelector(".text-cursor").style.display = "none";

    setTimeout(() => {
      this.isLoading = false;
    }, 15000);

    window.onscroll = function() {showHomeNav()};
    function showHomeNav() {
      if (document.documentElement.scrollTop < 300) {
        document.getElementById("nav-links-home").style.display = "none";
        document.getElementById("scrollbutton").style.opacity = "1";
      } else {
        document.getElementById("nav-links-home").style.display = "block";
        document.getElementById("scrollbutton").style.opacity = "0";
      }
    }

    const percentLabel = document.querySelector("#percent");
    window.addEventListener("scroll", () => {
      let scrollTop = window.scrollY;
      let docHeight = document.body.offsetHeight;
      let scrollPercent = scrollTop / docHeight;
      let scrollPercentRounded = Math.round(scrollPercent * 100);
      percentLabel.innerHTML = scrollPercentRounded;
    });
  }
}
</script>

<template>
 
  <body>
    <!-- <Transition name="fade">
      <LoadingScreen v-if="isLoading == true"/>
    </Transition> -->
    <main>
      <div class="home-view start-view">
        <h1>
          Design & Development
        </h1>
          <a href="#nav-view" class="link desktop" id="scrollbutton">scroll</a>
          <p id="scroll-percentage" class="desktop">
            <span id="percent">0</span>%
          </p>

      </div>

      <div class="home-view desktop" id="nav-view">
        <div id="nav-links-home">
          <router-link to="/work">
            work
          </router-link>
          <router-link to="/about">
            about
          </router-link>
          </div>
      </div>
    </main>
   
    <Sphere />

  </body>

</template>

<style scoped>
@media (min-width: 200px) {
  body{
    height: 100vh;
    width: 100vw;
    overflow-x: hidden;
    display: flex;
  }
  h1{
    font-size: 2rem;
    font-weight: 100;
    position: fixed;
  }
  
}
@media (min-width: 992px) {
    body{
      max-height: 200vh;
      overflow-y: scroll;
    }
    header{
        display: block;
    }
    .home-view{
      height: 100vh;
      width: 100vw;
      padding: 0;
      margin: 0;
      display: flex;
      flex-direction: row;
      align-items: center;
      justify-content: center;
    } 
    #nav-links-home{
      position: fixed;
      top: 45vh;
      left: 36vw;
      width: 30vw;
      display: none;
      z-index: 50000000;
    }
    #nav-view a{
    font-family: "sans-serif";
    src: url('src/assets/fonts/Ade-Display.otf')  format('opentype');
    display: inline-block;
    font-size: 3em;
    text-transform: uppercase;
    text-decoration: none;
    margin: 4%;
    }
    #nav-view a:hover, #nav-view a:focus {
    font-style: italic;
    }
    h1{
      font-size: 6.6rem;
      line-height: 1em;
      margin: 0;
      text-align: center;
    }
    #scrollbutton{
      position: fixed;
      background: none;
      font-family: "Brigade", sans-serif;
      font-size: 1em;
      text-decoration: none;
      top: 88vh;
      left: 49vw;
      border-bottom: 1px solid;
      z-index: 150;
    }
    #scrollbutton:hover{
      font-style: italic;
    }
    #scroll-percentage{
      position: fixed;
      top: 88vh;
      left: 90vw;
      z-index: 150;
    }
 
}  
</style>