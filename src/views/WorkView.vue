<script>
import SideNav from '../components/SideNav.vue'
import Cursor from '../components/Cursor.vue'

export default {
  props:{
    links: Array,
    navLinks: Array,
    sideNav: Array, 
    caseNav: Array
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
      text7: "none",
      line8: "0",
      text8: "none"
    }
  },
  mounted(){
    document.querySelector(".text-cursor").style.display = "none";

    this.sideNav.push("showSideNav")
    this.caseNav.push("hideSoMe")
  },
  methods:{
    revealCaseImg(image){
      document.querySelector("#work-img").style.backgroundImage = "url(" + image + ")";
      document.querySelector("#work-img").style.opacity = "1";
      document.querySelector("#work-img").style.transform = "scale(1.5, 1.5)";
    },
    hideCaseImg(){
      document.querySelector("#work-img").style.opacity = "0";
      document.querySelector("#work-img").style.transform = "scale(1, 1)";
    }
      
  }
  
}

</script>

<template>
<body>

  <div id="container">
    <div id="title">
      <h1>Work</h1>
    </div>
    <div id="work-img">
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
  <div id="work-links">
          <router-link to="/concreate" href="" class="work-link" @mouseover='revealCaseImg("src/assets/cases/concreate/Zine1.jpg"); text1 = "inline"; line1 = "9em"' @mouseleave="hideCaseImg(); text1 = 'none'; line1 = '0'">
            <h2>Gamél</h2> 
            <div class="line" :style="{ 'width': line1 }"></div>
            <h2 :style="{ 'display': text1}">Web Design</h2>
          </router-link>
          <router-link to="/concreate" href="" class="work-link" @mouseover='revealCaseImg("src/assets/cases/concreate/Zine6.jpg"); text2 = "inline"; line2 = "9em"' @mouseleave="hideCaseImg(); text2 = 'none'; line2 = '0'">
            <h2>HiTech</h2> 
            <div class="line" :style="{ 'width': line2 }"></div>
            <h2 :style="{ 'display': text2}">Web Design</h2>
          </router-link>
          <router-link to="/concreate" href="" class="work-link" @mouseover='revealCaseImg("src/assets/cases/concreate/Zine1.jpg"); text3 = "inline"; line3 = "9em"' @mouseleave="hideCaseImg(); text3 = 'none'; line3 = '0'">
            <h2>Concreate</h2> 
            <div class="line" :style="{ 'width': line3 }"></div>
            <h2 :style="{ 'display': text3}">Graphic Design</h2>
          </router-link>
          <router-link to="/concreate" href="" class="work-link" @mouseover='revealCaseImg("src/assets/cases/concreate/Zine1.jpg"); text4 = "inline"; line4 = "9em"' @mouseleave="hideCaseImg(); text4 = 'none'; line4 = '0'">
            <h2>Skilled</h2> 
            <div class="line" :style="{ 'width': line4 }"></div>
            <h2 :style="{ 'display': text4}">UI Design</h2>
          </router-link>
          <router-link to="/concreate" href="" class="work-link" @mouseover='revealCaseImg("src/assets/cases/concreate/Zine1.jpg"); text5 = "inline"; line5 = "9em"' @mouseleave="hideCaseImg(); text5 = 'none'; line5 = '0'">
            <h2>ToDo</h2> 
            <div class="line" :style="{ 'width': line5 }"></div>
            <h2 :style="{ 'display': text5}">Client-Server Code</h2>
          </router-link>
          <router-link to="/concreate" href="" class="work-link" @mouseover='revealCaseImg("src/assets/cases/concreate/Zine1.jpg"); text6 = "inline"; line6 = "9em"' @mouseleave="hideCaseImg(); text6 = 'none'; line6 = '0'">
            <h2>Baio</h2> 
            <div class="line" :style="{ 'width': line6 }"></div>
            <h2 :style="{ 'display': text6}">Brand & UI Design</h2>
          </router-link>
          <router-link to="/concreate" href="" class="work-link" @mouseover='revealCaseImg("src/assets/cases/concreate/Zine1.jpg"); text7 = "inline"; line7 = "9em"' @mouseleave="hideCaseImg(); text7 = 'none'; line7 = '0'">
            <h2>Sticky Notes</h2> 
            <div class="line" :style="{ 'width': line7 }"></div>
            <h2 :style="{ 'display': text7}"> Client-Server Code </h2>
          </router-link>
          <router-link to="/concreate" href="" class="work-link" @mouseover='revealCaseImg("src/assets/cases/concreate/Zine1.jpg"); text8 = "inline"; line8 = "9em"' @mouseleave="hideCaseImg(); text8 = 'none'; line8 = '0'">
            <h2>Nio Gin</h2> 
            <div class="line" :style="{ 'width': line8 }"></div>
            <h2 :style="{ 'display': text8}"> Brand & Package Design </h2>
          </router-link>
    </div>
    
  </div>
  
</body>
</template>

<style scoped>
@media (min-width: 1024px) {
/* General */
  body{
    overflow-y: hidden;
  }
  #container{
    width: 100vw;
    height: 100vh;
    display: flex;
    align-items: center;
    padding: 0 0 0 5vw;
  }
  #work-links{
    box-sizing: border-box;
    width: 80vw;
    height: 100vh;
    padding: 10vh 0 10vh 0;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    z-index: 100;
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
    /* Profile Image Animation */
    #work-img{
    position: absolute;
    box-sizing: border-box;
    margin-left: 60vw;
    height: 100vh;
    width: 35vw;
    background-position: center center;
    background-size: cover;
    background-repeat: no-repeat;
    opacity: 0;
    transition: all 1s ease;
  }
  #blobSvg{
    background-color: white;
    mix-blend-mode: screen; 
  }
  #d{
    filter: blur(10px);
    transform: scale(1.5, 1.5);
    transform-origin: top left;
  }
}

</style>
