<script>
import SideNav from '../components/SideNav.vue'
import PageNumberStyle from '../assets/pagenumbers.css'

export default {
  props:{
    
  },
  components: {
  },
  data() {
    return {
      show1: true,
      show2: false,
      width1: "40%",
      width2: "40%",
      width3: "40%",
      width4: "40%",
      PageNumberStyle
    }
  },
  mounted(){
    let container = document.querySelector("#container")
    document.querySelector(".text-cursor").style.display = "block"

    const mouseDown = (e) => {
        let x = e.clientX;
        let screenHalf = window.screen.width/2
        if(x < screenHalf){
          if(this.show1 === true){
            this.show1 = false,
            this.show2 = true
          }
          else if(this.show2 === true){
            this.show2 = false,
            this.show1 = true
          }
        }
        else if(x > screenHalf){
          if(this.show1 === true){
            this.show1 = false,
            this.show2 = true
          }
          else if(this.show2 === true){
            this.show2 = false,
            this.show1 = true
          }
        }           
    }
    window.addEventListener("click", mouseDown);
  },
  methods:{
    pageNumberStyle: function(){
    console.log(this.show)
    if(this.show1 === true){
      document.querySelector("#page-number-1").style.fontStyle= "oblique";
      document.querySelector("#page-number-1").style.fontWeight= "700";
      document.querySelector("#page-number-1").style.border= "1px solid red";
    }
    else if(this.show2 === true){
      document.querySelector("#page-number-2").style.fontStyle= "normal";
      document.querySelector("#page-number-2").style.margin= "0 0 0 5%";
      document.querySelector("#page-number-2").style.border= "1px solid yellow";
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
    <div v-if="show1" class="page" id="page1">
      <h1>About</h1>
      <div id="profile-img">
        <svg class="blob"  preserveAspectRatio="none" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" height="100%" width="100%" id="blobSvg">
        <path  id="d" fill="black">
          <animate attributeName="d" dur="20000ms" repeatCount="indefinite" values="
          M421.5,288Q407,326,399,376.5Q391,427,342,432.5Q293,438,262.5,382.5Q232,327,218,317Q204,307,121,329.5Q38,352,63.5,301Q89,250,69,201.5Q49,153,80.5,115Q112,77,157,58.5Q202,40,237.5,95.5Q273,151,302.5,149Q332,147,374,158.5Q416,170,426,210Q436,250,421.5,288Z;
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
    <div v-if="show2" class="page" id="page2">
      <div id="about-me">
        <h2>about me </h2>
        <p>
          Hello, I’m Pauline Wahle - creative designer and developer.<br> Coming from a German degree in graphic and object design, I continued to focus on digital spaces with studies in user experience and front-end development. Always considering usability aspects, I find it fascinating to explore and reimagine digital spaces in new ways that surprise, entertain, simplify and create lasting impressions. By taking opportunities to establish original ideas, each design can get a unique look and feel. With a wholistic design sense of shape and space from experience in both disciplines, the lines between conventional and interactive design are blurry, both can profit from each other. My basis for both design and development is <b> creative thinking</b>, to stay flexible, keep moving and find alternative paths.  
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
      <button @click="this.show1 = true; this.show2 = false;" id="page-number-1">1</button>
      <button @click="this.show1 = false; this.show2 = true;" id="page-number-2">2</button>
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
    height: 90vh;
    display: flex;
    padding: 0 0 0 5vw;
    border: 1px solid;
  }
  .page{
    height: 100vh;
    width: 100vw;
    display: flex;
    align-items: center;
  }
  #page1{
    position: absolute;
  }
  /* Profile Image Animation */
  #profile-img{
    box-sizing: border-box;
    margin-left: 35vw;
    height: 100vh;
    width: 35vw;
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


  h1{
    line-height: .8em;
    z-index: 50;
    font-style: italic;
  }
  h2{
    font-weight: 200;
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


#page2{
    position: absolute;
    z-index: 100;
    margin: 0 0 0 25vw;
  }

  #about-me{
    display: block;
    height: 80vh;
    width: 30vw;
    text-align: justify;
  text-justify: inter-word;
  }
  #about-my{
    display: block;
    height: 80vh;
    width: 25vw;
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
