<script>
    export default{
      props:{
        links: Array,
        sideNav: Array
      },
      mounted(){
        this.links.push(document.querySelector(".link"))
        
      }
      
    }
    


</script>
<template>

<aside>
  <nav>
  <!-- <div v-if="this.caseNav.length == 0"> -->
    <div id="so-me">
      <a href = "mailto:abc@example.com">
        LinkedIn
      </a>
      <a href = "mailto:abc@example.com">
        Github
      </a>
      <a href = "mailto:abc@example.com">
        Pinterest
      </a>
      <a href = "mailto:abc@example.com">
        Codepen
      </a>
    </div>
  <!-- </div> -->

    <div id="main-nav">
    <router-link to="/" id="menu-button" class="link">
      Menu
    </router-link> 
    <h3>
      Get in touch
    </h3>
    <a href = "mailto:abc@example.com">
      paulinewahle@mail.com
    </a>
    </div>
  </nav>
</aside>
</template>

<style scoped>
    aside{
      position: fixed;
      width: 20vw;
      height: 100vh;
      box-sizing: border-box;
      padding: 10vh 0 10vh 5vw;
      z-index: 200;
    }
    nav{
      height: 100%;
      display: flex; 
      flex-direction: column;
      justify-content: flex-end;
    }
    h3{
      width: 100%;
      margin: 35% 0 0;
    }
    a{
      text-decoration: none;
      font-weight: light;
      display: block;
      margin: .5em 0 0 0;
    }
    a:hover{
      font-style: oblique;
    }
    #so-me{
      margin: 0 0 45vh 0;
    }
    #menu-button{
      font-size: 1.5em;
      width: 3.4em;
      height: 1.5em;
      background: none;
      border: none;
      border-bottom: 2px solid #292929;
      padding: 0;
      text-align: start;
      font-family: "Brigade", sans-serif;
      font-weight: bold;
      text-transform: uppercase;
      transition: all 1s ease;
    }
    #menu-button:hover{
      width: 100%;
      font-style: oblique;
      border-bottom: 1px solid #292929;
    }
</style>