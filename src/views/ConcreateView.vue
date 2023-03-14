<script lang>
import CaseNav from '../components/CaseNav.vue'
import PageNumberStyle from '../assets/pagenumbers.css'

export default {
  props:{
    caseNav: Array,
  },
  components: {
  },
  data() {
    return {
      show1: true,
      show2: false,
      show3: false,
      show4: false,
      show5: false,
      show6: false,
      show7: false,
      img1: "url('src/assets/cases/concreate/Zine1.jpg')",
      img2: "url('src/assets/cases/concreate/Zine2.jpg')",
      img21: "url('src/assets/cases/concreate/Zine2.1.jpg')",
      img3: "url('src/assets/cases/concreate/Zine3.jpg')",
      img31: "url('src/assets/cases/concreate/Zine3.1.jpg')",
      img4: "url('src/assets/cases/concreate/Zine4.jpg')",
      img5: "url('src/assets/cases/concreate/Zine5.jpg')",
      img6: "url('src/assets/cases/concreate/Zine6.jpg')",
      img61: "url('src/assets/cases/concreate/Zine6.1.jpg')",
      img7: "url('src/assets/cases/concreate/Zine7.jpg')",

    }
  },
  mounted(){
    this.caseNav.push("hideSoMe")

    document.querySelector(".text-cursor").style.display = "block";

    const mouseDown = (e) => {
        let x = e.clientX;
        let screenHalf = window.screen.width/2
        if(x < screenHalf){
          if(this.show1 === true){
            this.show1 = false,
            this.show7 = true
          }
          else if(this.show2 === true){
            this.show2 = false,
            this.show1 = true
          }
          else if(this.show3 === true){
            this.show3 = false,
            this.show2 = true
          }
          else if(this.show4 === true){
            this.show4 = false,
            this.show3 = true
          }
          else if(this.show5 === true){
            this.show5 = false,
            this.show4 = true
          }
          else if(this.show6 === true){
            this.show6 = false,
            this.show5 = true
          }
          else if(this.show7 === true){
            this.show7 = false,
            this.show6 = true
          }
        }
        else if(x > screenHalf){
          if(this.show1 === true){
            this.show1 = false,
            this.show2 = true
          }
          else if(this.show2 === true){
            this.show2 = false,
            this.show3 = true
          }
          else if(this.show3 === true){
            this.show3 = false,
            this.show4 = true
          }
          else if(this.show4 === true){
            this.show4 = false,
            this.show5 = true
          }
          else if(this.show5 === true){
            this.show5 = false,
            this.show6 = true
          }
          else if(this.show6 === true){
            this.show6 = false,
            this.show7 = true
          }
          else if(this.show7 === true){
            this.show7 = false,
            this.show1 = true
          }
        }           
    }
    window.addEventListener("click", mouseDown);
  },
  methods:{

  }
  
}

</script>

<template>
<Transition name="slide-fade">
<body>
  <div id="responsive-container">
    <h1>Concreate</h1>
    <div class="resp-case-img" :style="{'background-image':img1}"/>
    <div class="resp-case-img" :style="{'background-image':img2}"/>
    <div class="resp-case-img" :style="{'background-image':img21}"/>
    <video autoplay loop mute>
        <source src="src/assets/cases/concreate/Zine5.1.mov" type="video/mp4">
    </video>
    <div class="resp-case-img" :style="{'background-image':img3}"/>
    <div class="resp-case-img" :style="{'background-image':img31}"/>
    <div class="resp-case-img" :style="{'background-image':img4}"/>
    <div class="resp-case-img" :style="{'background-image':img5}"/>
    <div class="resp-case-img" :style="{'background-image':img6}"/>
    <div class="resp-case-img" :style="{'background-image':img61}"/>
    <div class="resp-case-img" :style="{'background-image':img7}"/>
  </div>
  <div id="desktop-container">
    <h1>Concreate</h1>
    <Transition name="slide-fade">
    <div v-if="show1" class="page" id="page1">
      <div id="descr">
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Earum odit, veritatis hic delectus sit, neque ab exercitationem.</p>
      <a href="src/assets/cases/concreate/concreate.epub" download="EPUB" :style="{'z-index':'100'}"> 
        GET E-PUBLICATION
      </a>
    </div>
      <div alt="zine-image" class="img cover-img" :style="{'background-image':img1}"></div>
    </div>
    </Transition>
    <Transition name="slide-fade">
    <div v-if="show2" class="page" id="page2">
      <div alt="zine-image" class="img landscape-img" :style="{'background-image':img2}"></div>
      <div alt="zine-image" class="img profile-img" :style="{'background-image':img21}"></div>
    </div>
    </Transition>
    <Transition name="slide-fade">
    <div v-if="show3" class="page" id="page3">
      <video autoplay loop>
        <source src="src/assets/cases/concreate/Zine5.1.mov" type="video/mp4">
      </video>
      <div alt="zine-image" class="img landscape-img" :style="{'background-image':img5}"></div>
    </div>
    </Transition>
    <Transition name="slide-fade">
    <div v-if="show4" class="page" id="page4">
      <div alt="zine-image" class="img cover-img" :style="{'background-image':img4}"></div>
    </div>
    </Transition>
    <Transition name="slide-fade">
    <div v-if="show5" class="page" id="page5">
      <div alt="zine-image" class="img landscape-img" :style="{'background-image':img3}"></div>
      <div alt="zine-image" class="img profile-img" :style="{'background-image':img31}"></div>
    </div>
    </Transition>
    <Transition name="slide-fade">
    <div v-if="show6" class="page" id="page6">
      <div alt="zine-image" class="img landscape-img" :style="{'background-image':img6}"></div>
      <div alt="zine-image" class="img profile-img" :style="{'background-image':img61}"></div>
    </div>
    </Transition>
    <Transition name="slide-fade">
    <div v-if="show7" class="page" id="page7">
      <div alt="zine-image" class="img cover-img" :style="{'background-image':img7}"></div>
    </div>
    </Transition>

    
    
    <div id="page-numbers">
      <button @click="show2 = false; show3 = false; show4 = false; show5 = false; show6 = false; show7 = false; show1 = true;" id="page-number-1">1</button>
      <button @click="show1 = false; show3 = false; show4 = false; show5 = false; show6 = false; show7 = false; show2 = true;" id="page-number-2">2</button>
      <button @click="show1 = false; show2 = false; show4 = false; show5 = false; show6 = false; show7 = false; show3 = true;" id="page-number-3">3</button>
      <button @click="show1 = false; show2 = false; show3 = false; show5 = false; show6 = false; show7 = false; show4 = true;" id="page-number-4">4</button>
      <button @click="show1 = false; show2 = false; show3 = false; show4 = false; show6 = false; show7 = false; show5 = true;" id="page-number-5">5</button>
      <button @click="show1 = false; show2 = false; show3 = false; show4 = false; show5 = false; show7 = false; show6 = true;" id="page-number-6">6</button>
      <button @click="show1 = false; show2 = false; show3 = false; show4 = false; show5 = false; show6 = false; show7 = true;" id="page-number-7">7</button>
    </div>
  </div>

</body>
</Transition>
</template>

<style scoped>
@media only screen and (max-width: 768px) {

  body{
    width: 100vw;
    overflow-y: scroll;
    overflow-x: hidden;
  }
  #desktop-container{
    display: none,
  }
  #responsive-container{
    padding: 30% 10%;
  }
  #page-numbers{
    display: none;
  }
  h1{
    position: fixed;
    font-size: 5em;
    z-index: 100;
    top: 10vh;
  }
  p,a {
      font-size: 2em;
      text-decoration: none;
  }
  .resp-case-img, video{
    width: 80vw;
    height: 40vh;
    margin: 10% 0;
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center center;
  }
}
@media (min-width: 1024px) {
  

/* General */
  body{
    overflow: hidden;
  }
  #desktop-container{
    width: 100vw;
    height: 100vh;
  }
  .page{
    position: absolute;
    height: 100%;
    width: 100%;
    padding: 10vh 0 10vh 20vw;
    display: flex;
    box-sizing: border-box;
  }
  h1{
    margin: 10vh 0 0 3vw;
    font-size: 10rem;
    font-weight: 100;
    position: fixed;
    z-index: 500;
  }
  #descr{
    margin: 26vh 0 0 -15vw;
    width: 30vw;
    position: absolute;
    z-index: 500;
  }
  p,a {
    font-size: 1.4rem;
    text-decoration: none;
  }
  a:hover{
    font-style: italic;
  }
  .img{
    height: 80vh;
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center center;
  }
  .cover-img{
    width: 80vw;
  }
  .landscape-img{
    width: 60vw;
  }
  .profile-img{
    width: 20vw;
    margin-left: 1vw;
  }


  
}

</style>
