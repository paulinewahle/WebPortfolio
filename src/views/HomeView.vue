<script lang>
import Sphere from '../components/Sphere.vue'
import LoadingScreen from "../components/LoadingScreen.vue"
import Header from '../components/Header.vue'

export default{
  props:{
    sideNav: Array
  },
  components: {
    Sphere,
    LoadingScreen,
    Header
  },
  data(){
    return {
      isLoading: true,
    }
  },
  mounted() {

    setTimeout(() => {
      this.isLoading = false;
    }, 15000);

    window.onscroll = function() {showHomeNav()};
    function showHomeNav() {
      if (document.documentElement.scrollTop < 110) {
        document.getElementById("nav-links-home").style.display = "none";
      } else {
        document.getElementById("nav-links-home").style.display = "block";
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
    <Header></Header>
    <main>
      <div class="home-view start-view">
          
       <h1>Design & 
        Development
                </h1>
         
          <a href="#nav-view" class="link" id="scrollbutton">scroll</a>
          <p id="scroll-percentage">
            <span id="percent">0</span>%
          </p>

      </div>

      <div class="home-view nav-view">
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
@media (min-width: 1024px) {
    body{
      max-height: 200vh;
    }
    .home-view{
      height: 100vh;
      width: 100vw;
      padding: 0;
      margin: 0;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      border: 1px solid blueviolet;
    }
    .nav-view{
      border: 1px solid red;
      /* position: fixed; */
      z-index: 50000000;
    }
    #nav-links-home{
      width: 100vw;
      display: flex;
      flex-direction: row;
      justify-content: center;
    }
    #nav-view a{
    display: inline-block;
    font-size: 3em;
    font-family: 'serif';
    text-decoration: none;
    margin: 4%;
    }
    #nav-view a:hover, #nav-view a:focus {
    font-style: italic;
    }
    h1{
      font-size: 7rem;
      font-weight: 200;
      line-height: 1em;
      margin: 0;
      position: fixed;
    }
    #scrollbutton{
      position: fixed;
      background: none;
      font-family: "Brigade", sans-serif;
      font-size: 1em;
      text-decoration: none;
      top: 88vh;
      left: 47vw;
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