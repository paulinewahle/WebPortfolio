<script>
import 'vue-horizontal-scroll/dist/vue-horizontal-scroll.css'
import SideNav from '../components/SideNav.vue'
import Cursor from '../components/Cursor.vue'

export default {
  props:{
    links: Array,
    navLinks: Array,
    sideNav: Array, 
    // caseNav: Array
  },

  components: {
      SideNav,
      Cursor
  },
  data() {
    return {
      line1: "0",
      text1: "none",
      line2: "0",
      text2: "none",
      line3: "0",
      text3: "none",
      line4: "0",
      text4: "none",
      line5: "0",
      text5: "none",
      line6: "0",
      text6: "none",
      line7: "0",
      text7: "none"
    }
  },
  mounted(){
        
      this.sideNav.push("showSideNav")
      // this.caseNav.pop("activeCaseNav")
  },
  methods:{
    pageNumberStyle: function(){
    if(this.show0 === true){
      document.querySelector("#page-number-0").style.fontStyle= "oblique";
      document.querySelector("#page-number-0").style.fontWeight= "700";
      document.querySelector("#page-number-0").style.border= "1px solid red";
    }
    else if(this.show1 === true){
      document.querySelector("#page-number-0").style.fontStyle= "normal";
      document.querySelector("#page-number-0").style.margin= "0 0 0 5%";
      document.querySelector("#page-number-0").style.border= "1px solid yellow";
    }
    },
    function(){
    }
      
  }
  
}

</script>

<template>
<body>

  <div id="container">
    <div id="title">
      <h1>Wo<br>-rk</h1>
      
    </div>
    <div id="work-links">
          <router-link to="/concreate" href="" class="work-link" @mouseover="text1 = 'inline'; line1 = '9em'" @mouseleave="text1 = 'none'; line1 = '0'">
            <h2>Concreate</h2> 
            <div class="line" :style="{ 'width': line1 }"></div>
            <h2 :style="{ 'display': text1}">Graphic Design</h2>
          </router-link>
          <a href="" class="work-link" @mouseover="text2 = 'inline'; line2 = '9em'" @mouseleave="text2 = 'none'; line2 = '0'">
            <h2>Gamél</h2> 
            <div class="line" :style="{ 'width': line2 }"></div>
            <h2 :style="{ 'display': text2}">Graphic Design</h2>
          </a>
          <a href="" class="work-link" @mouseover="text3 = 'inline'; line3 = '9em'" @mouseleave="text3 = 'none'; line3 = '0'">
            <h2>HiTech</h2> 
            <div class="line" :style="{ 'width': line3 }"></div>
            <h2 :style="{ 'display': text3}">Graphic Design</h2>
          </a>
          <a href="" class="work-link" @mouseover="text4 = 'inline'; line4 = '9em'" @mouseleave="text4 = 'none'; line4 = '0'">
            <h2>NioGin</h2> 
            <div class="line" :style="{ 'width': line4 }"></div>
            <h2 :style="{ 'display': text4}">Graphic Design</h2>
          </a>
          <a href="" class="work-link" @mouseover="text5 = 'inline'; line5 = '9em'" @mouseleave="text5 = 'none'; line5 = '0'">
            <h2>Skivs</h2> 
            <div class="line" :style="{ 'width': line5 }"></div>
            <h2 :style="{ 'display': text5}">Graphic Design</h2>
          </a>
          <a href="" class="work-link" @mouseover="text6 = 'inline'; line6 = '9em'" @mouseleave="text6 = 'none'; line6 = '0'">
            <h2>Upsave</h2> 
            <div class="line" :style="{ 'width': line6 }"></div>
            <h2 :style="{ 'display': text6}">Graphic Design</h2>
          </a>
          <a href="" class="work-link" @mouseover="text7 = 'inline'; line7 = '9em'" @mouseleave="text7 = 'none'; line7 = '0'">
            <h2>Upsave</h2> 
            <div class="line" :style="{ 'width': line7 }"></div>
            <h2 :style="{ 'display': text7}">Graphic Design</h2>
          </a>
    </div>
  </div>
      
</body>
</template>

<style scoped>
@media (min-width: 1024px) {

/* General */
  body{
    overflow: hidden;
  }
  #container{
    width: 100vw;
    height: 100vh;
    display: flex;
    align-items: center;
    padding: 0 0 0 20vw;
  }
  #work-links{
    box-sizing: border-box;
    width: 60vw;
    height: 100vh;
    padding: 10vh 0 10vh 0;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }
  .work-link{

    text-decoration: none;
    display: flex;
    padding-left: 40%;
    transition: all .7s ease;
  }
  .work-link:hover{
    font-style: oblique;
    padding-left: 0%;
    opacity: 1;
  }

  .line{
    border-bottom: 1px solid #262626;
    display: inline-block;
    margin: 0 5% 0 5%;
    height: .9rem;
    transition: width .7s ease;
  }
  
}

</style>
