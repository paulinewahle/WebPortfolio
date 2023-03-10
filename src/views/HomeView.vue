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
    window.onscroll = function() {myFunction()};

    function myFunction() {
      if (document.documentElement.scrollTop < 110) {
        document.getElementById("navLinksHome").style.display = "none";
      } else {
        document.getElementById("navLinksHome").style.display = "block";
      }
    }
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
    <div class="homeView startView">
      
        <pre><h1>
          
    Design & 
        Development
              </h1>
        </pre>
      
        <a href="#navView" class="link" id="scrollbutton">scroll</a>
    </div>
    <div id="navView">
      <div id="navLinksHome">
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
    .homeView{
      height: 50vh;
      width: 100vw;
      padding: 0;
      margin: 0;
      display: flex;
      flex-direction: column;
      align-items: right;
      justify-content: right;
      border: 1px solid blueviolet;
    }
    #navView{
      border: 1px solid red;
      align-items: center;
      position: fixed;
      z-index: 50000000;
    }
    #navLinksHome{
      width: 100vw;
      display: flex;
      flex-direction: row;
      justify-content: center;
    }
    #navView a{
    display: inline-block;
    font-size: 3em;
    font-family: 'serif';
    text-decoration: none;
    margin: 4%;
    }
    #navView a:hover, #navView a:focus {
    font-style: italic;
    }
    h1{
      font-size: 7rem;
      font-weight: 200;
      line-height: 1em;
      margin: 0;
      position: fixed;
      top: 1vh;
      right: 10vw;
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

 
}  
</style>