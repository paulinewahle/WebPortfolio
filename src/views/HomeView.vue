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
      
        <!-- <button class="link" id="scrollbutton">scroll</button>
        <button v-on:click="greet">hover</button> -->
    </div>
    <div class="homeView navView">
      
      <router-link to="/work">
        work
      </router-link>
      <router-link to="/work">
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
      width: 100vw;
      height: 200vh;
    }
    main{
      overflow-y: scroll;
      scroll-snap-type: both mandatory;
    }
    .homeView{
      height: 100vh;
      width: 100vw;
      padding: 0;
      margin: 0;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      border: 1px solid blueviolet;
      overflow-y: scroll;
      scroll-snap-align: center;
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
    }
  .link{
      border: 1px solid red;
  }
 
}  
</style>