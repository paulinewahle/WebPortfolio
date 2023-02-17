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
    this.sideNav.pop("showSideNav")

    setTimeout(() => {
      this.isLoading = false;
    }, 15000);
  }
}
</script>

<template>
 
  <body>
    <!-- <Transition name="fade">
      <LoadingScreen v-if="isLoading == true"/>
    </Transition> -->
    <!-- <Header></Header> -->
    <main>
    <div class="homeView startView">
      
        <pre><h1>
Design & 
    Development
              </h1>
        </pre>
      
        <a href="#navView" class="link" id="scrollbutton">scroll</a>
    </div>
    <div class="homeView" id="navView">
      
      <router-link to="/work">
        work
      </router-link>
      <router-link to="/about">
        about
      </router-link>
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
    main{
      scroll-snap-type: both mandatory;
    }
    .homeView{
      height: 100vh;
      width: 100vw;
      padding: 0;
      margin: 0;
      display: flex;
      flex-direction: column;
      align-items: right;
      justify-content: right;
      border: 1px solid blueviolet;
      scroll-snap-align: start;
    }
    .navView{
      z-index: 3000000;
      border: 1px solid red;
      color: #eeeeee;
    }
    h1{
      font-size: 12rem;
      font-weight: 200;
      line-height: 1em;
      margin: 0;
      font-style: italic;
      position: fixed;
      top: 1vh;
      right: 10vw;
    }
    #scrollbutton{
      /* border: none; */
      background: none;
      border-bottom: 1px solid black;
      font-family: "Brigade", sans-serif;
      font-size: 1em;
      text-align: end;
      z-index: 500000;
    }
    #scrollbutton:hover{
      background-color: yellow;
    }
  .link{
      border: 1px solid red;
  }
 
}  
</style>