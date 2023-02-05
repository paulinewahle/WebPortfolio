<script>
import HorizontalScroll from 'vue-horizontal-scroll'
import 'vue-horizontal-scroll/dist/vue-horizontal-scroll.css'
import Nav from '../components/SideNav.vue';

export default {
  props:{
    sideNav: Array
  },
  components: {
      HorizontalScroll, 
      Nav
  },
  data() {
    return {
      show0: true,
      show1: false,
      width1: "40%",
      width2: "40%",
      width3: "40%",
      width4: "40%",

    }
  },
  mounted(){
    this.sideNav.push("showSideNav")
  },
  methods:{
    pageNumberStyle: function(){
    console.log(this.show)
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
    }
    
     
      
  }
  
}

</script>

<template>
<body>
  
  <Nav></Nav>
  <div id="container">
    <Transition name="slide-fade">
    <div v-if="show0" class="page" id="page1">
      <h1>Ab-<br>out</h1>
      <div id="profile-img">
        <svg class="blob"  preserveAspectRatio="none" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" height="100%" width="100%" id="blobSvg">
        <path  id="d" fill="black">
          <animate attributeName="d" dur="20000ms" repeatCount="indefinite" values="
          M421.5,288Q407,326,399,376.5Q391,427,342,432.5Q293,438,262.5,382.5Q232,327,218,317Q204,307,121,329.5Q38,352,63.5,301Q89,250,69,201.5Q49,153,80.5,115Q112,77,157,58.5Q202,40,237.5,95.5Q273,151,302.5,149Q332,147,374,158.5Q416,170,426,210Q436,250,421.5,288Z;
          M425,299.5Q455,349,377,330Q299,311,290.5,350.5Q282,390,238.5,441Q195,492,158.5,451.5Q122,411,117,363.5Q112,316,85,283Q58,250,54,202Q50,154,77.5,111Q105,68,169,122Q233,176,258.5,138.5Q284,101,288,149.5Q292,198,361,180.5Q430,163,412.5,206.5Q395,250,425,299.5Z;
          M396,262Q301,274,324.5,323.5Q348,373,315.5,383.5Q283,394,256,367.5Q229,341,216.5,324Q204,307,129,325.5Q54,344,30,297Q6,250,40,207.5Q74,165,134.5,173Q195,181,198,109Q201,37,242.5,68Q284,99,292,143Q300,187,361,177Q422,167,456.5,208.5Q491,250,396,262Z;
          M412,302Q465,354,386.5,338.5Q308,323,286.5,320Q265,317,246,334.5Q227,352,213.5,332Q200,312,126.5,328.5Q53,345,61.5,297.5Q70,250,135.5,238Q201,226,152,145.5Q103,65,156,66.5Q209,68,238.5,120Q268,172,312.5,143.5Q357,115,385.5,143Q414,171,386.5,210.5Q359,250,412,302Z;
          M396.5,289Q412,328,388.5,361Q365,394,315.5,358Q266,322,235,387Q204,452,197.5,388.5Q191,325,193,300.5Q195,276,187.5,263Q180,250,176,231.5Q172,213,142.5,145.5Q113,78,158,62Q203,46,243.5,74Q284,102,332,94Q380,86,368.5,142.5Q357,199,369,224.5Q381,250,396.5,289Z;
          M326,267.5Q323,285,361,361Q399,437,341.5,419Q284,401,242,435.5Q200,470,157,445Q114,420,73,387.5Q32,355,56,302.5Q80,250,136.5,236.5Q193,223,165.5,166.5Q138,110,171,78.5Q204,47,250.5,45.5Q297,44,312.5,98Q328,152,328.5,182Q329,212,329,231Q329,250,326,267.5Z;
          M424.5,276.5Q361,303,337.5,317Q314,331,304.5,389.5Q295,448,254,431Q213,414,175.5,402Q138,390,85,372.5Q32,355,64,302.5Q96,250,130.5,229.5Q165,209,159.5,169.5Q154,130,180.5,95Q207,60,248,69Q289,78,306.5,117.5Q324,157,389.5,154Q455,151,471.5,200.5Q488,250,424.5,276.5Z;
          M421.5,288Q407,326,399,376.5Q391,427,342,432.5Q293,438,262.5,382.5Q232,327,218,317Q204,307,121,329.5Q38,352,63.5,301Q89,250,69,201.5Q49,153,80.5,115Q112,77,157,58.5Q202,40,237.5,95.5Q273,151,302.5,149Q332,147,374,158.5Q416,170,426,210Q436,250,421.5,288Z;
            ">
          </animate>
        </path>
      </svg>
      </div>
    </div>
    </Transition>
    <Transition name="slide-fade">
    <div v-if="show1" class="page" id="page2">
      <div id="about-me">
        <h2>about me </h2>
        <p>
        Hi, it’s Pauline. <br>
        German, living in Sweden, I am a graphic designer, web developer and everything in-between. With a focus on digital interfaces, I orientate my skills and perspectives towards ever new ways of crafting impressions.
        I take opportunities to establish original ideas and to find new ways of building well understood experiences that are being remembered for their unique look and feel.
        </p> 
      </div>
      <div id="about-my">
        <h2>about my </h2>
        <div id="links-wrapper">
        <div class="wrapper">
          <h4> Experience & Education </h4>
          <a href="" class="about-link" @mouseover="width1 = '80%'" @mouseleave="width1 = '40%'">
            <div class="line" :style="{ 'width': width1 }"></div><p>LinkedIn</p>
          </a>
        </div>
        <div class="wrapper">
          <h4> Front-End Code </h4>
            <a href="" class="about-link" @mouseover="width2 = '70%'" @mouseleave="width2 = '40%'">
              <div class="line" :style="{ 'width': width2 }"></div><p>Codepen</p>
            </a>
        </div>
        <div class="wrapper">
          <h4> Design & Animations </h4>
          <a href="" class="about-link" @mouseover="width3 = '70%'" @mouseleave="width3 = '40%'">
            <div class="line" :style="{ 'width': width3 }"></div><p>Pinterest</p>
          </a>
        </div>
        <div class="wrapper">
          <h4> Client-Server Code </h4>
          <a href="" class="about-link" @mouseover="width4 = '70%'" @mouseleave="width4 = '40%'">
            <div class="line" :style="{ 'width': width4 }"></div><p>Github</p>
          </a>
        </div>
      </div>
      </div>
      
    </div>
    </Transition>
    <Transition name="slide-fade">

    </Transition>
    <div id="page-numbers">
      <button @click="this.show0 = true; this.show1 = false;" id="page-number-0">0</button>
      <button @click="this.show0 = false; this.show1 = true;" id="page-number-1">1</button>
    </div>
  </div>
</body>
</template>

<style scoped>
@media (min-width: 1024px) {

/* Slide Page Animation */
.slide-fade-enter-active {
  transition: all 1s cubic-bezier(1, 0.5, 0.8, 1);
}

.slide-fade-leave-active {
  transition: all 1s cubic-bezier(1, 0.5, 0.8, 1);
}

.slide-fade-enter-from{
  transform: translateX(100vw);
  opacity: 0;
}
.slide-fade-leave-to {
  transform: translateX(-100vw);
  opacity: 0;
}
/* General */
  body{
    overflow: hidden;
    background-color: white;
  }
  
  #container{
    width: 100vw;
    height: 100vh;
    display: flex;
    align-items: center;
  }
  .page{
    height: 100vh;
    width: 100vw;
    display: flex;
    align-items: center;
  }
  #page1{
    position: absolute;
    box-sizing: border-box;
    padding: 0 0 0 20vw;
  }
  /* Profile Image Animation */
  #profile-img{
    box-sizing: border-box;
    margin-left: -10vw;
    height: 100vh;
    width: 40vw;
    background-image: url("src/assets/img/profile.jpg");
    background-position: center center;
    background-size: cover;
    background-repeat: no-repeat;
  }
  #blobSvg{
    background-color: white;
    mix-blend-mode: screen; 
  }
  path{
    filter: blur(10px);
    transform: scale(1.5, 1.5);
    transform-origin: top left;
  }
  #blobSvg2{
    margin-top: 10vh;
    filter: blur(0px);
    transform: scale(.5, .5);
    transform-origin: bottom right;
    outline: 30px solid red;
  }

  h1{
    line-height: .8em;
    font-size: 25rem;
    z-index: 50;
    font-style: italic;
  }
  h2{
    font-family: "PP Right Sans", sans-serif;
    font-weight: 200;
    font-style: italic;
    font-size: 1.5rem;
    margin: 0 0 15% 0;
    height: 10%;
  }
  h4{
    font-size: 1.5em;
    margin: 0 0 5% 0;

  }
  p,a {
    font-size: 1.4rem;
    margin: 0;
    text-decoration: none;
    
  }
  a:hover{
    font-style: italic;
  }
  /* Page Numbers */
  #page-numbers{
  height: 100vh;
  width: 20vw;
  padding-bottom: 10vh;
  box-sizing: border-box;
  position: fixed;
  display: flex;
  align-items: flex-end;
  z-index: 200;
  margin-left: 85vw;
}

#page-numbers button{
  font-size: 1.5rem;
  font-weight: 200;
  color: #262626;
  border: none;
  margin: 0 5%;
  transition: margin 1s ease;
}
#page-numbers button:hover{
  font-style: oblique;
  
}

#page2{
    position: absolute;
    z-index: 100;
    margin: 0 0 0 25vw;
  }

  #about-me, #about-my{
    display: block;
    height: 80vh;
    width: 20vw;
    box-sizing: border-box;

  }
  #about-me{
    padding-right: 2.5vw;

  }
  #about-my{
    padding-left: 2.5vw;
  }
  #links-wrapper{
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    height: 60vh;
  }
  .about-link{
    width: 100%;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
  }
  .line{
    border-bottom: 1px solid #262626;
    display: inline-block;
    margin: 0 10% 0 0 ;
    height: .9rem;
    transition: width .3s ease;
  }
  
}

</style>
