<script lang>
import CaseNav from '../components/CaseNav.vue'

export default {
  props:{
    sideNav: Array,
  },
  components: {
    CaseNav
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
<Transition name="slide-fade">
<body>
  
  <div id="container">
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
    <Transition name="slide-fade">
    <div v-if="show8" class="page" id="page8">
      
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
@media (min-width: 1024px) {

/* General */
  body{
    overflow: hidden;
  }
  
  #container{
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
    font-size: 15rem;
    font-style: italic;
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
  /* Page Numbers */
  #page-numbers{
  position: fixed;
  top: 93vh;
  width: 20vw;
  box-sizing: border-box;

  z-index: 200;
  margin-left: 75vw;
}

#page-numbers button{
  font-family: 'Right Sans Light';
  font-size: 1.5rem;
  color: #262626;
  border: none;
  
  transition: margin 1s ease;
  font-style: oblique;
}
#page-numbers button:hover, button:focus{
  margin: 0 .9em 0 0;
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
