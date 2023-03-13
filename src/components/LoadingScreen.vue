<script>
export default {
  name: "LoadingScreen",
  data(){
    return {
      id: 1,
      //item: document.getElementById("intro-loop-item"+id)
    }
  },
  mounted() {
    let id = 0
    
    const loadingInterval = setInterval(displayIntroItem, 2000)
    function displayIntroItem() {
      console.log(id)
      id++
      let item = document.getElementById("intro-loop-item"+id)
      item.style.display = "block"
      setTimeout(() => {
        item.style.display = "none"
      }, 1900)

      if (id>=6){
      clearInterval(loadingInterval)
      }
    }
    
  
    
  }
}

</script>

<template>
    <div id="loading">
      <ul>
        <li class="intro-loop-item" id="intro-loop-item1">
          <span class="a">Design</span> <span class="b">Concepts</span>
        </li>
        <li class="intro-loop-item" id="intro-loop-item2">
          <span class="b">Creative</span> <span class="a">Development</span>
        </li>
        <li class="intro-loop-item" id="intro-loop-item3">
          <span class="a">Web</span> <span class="b">Design</span>
        </li>
        <li class="intro-loop-item" id="intro-loop-item4">
          <span class="b">User</span> <span class="a">Experience</span>
        </li>
        <li class="intro-loop-item" id="intro-loop-item5">
          <span class="a">Graphic</span> <span class="b">Design</span>
        </li>
        <li class="intro-loop-item" id="intro-loop-item6">
          <span class="b">Digital</span> <span class="a">Interfaces</span>
        </li>
      </ul>
    </div>
</template>
  
<style scoped>
  #loading {
    position: absolute;
    z-index: 10000000;
    background-color: #eeeeee;
    height: 100vh;
    width: 100vw;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 1.5em;
  }

  ul{
    list-style-type: none;
    margin: 0;
    padding: 0;
    display: inline;
    text-align: center;
  }
  .intro-loop-item{
    display: none;
    position: relative;
    animation: fade 2s;
  }
  @keyframes fade{
    0%   {
      filter: blur(5px);
      opacity: 0;
    }
    50%  {
      filter: blur(0px);
      opacity: 1;
    }
    100% {
      filter: blur(5px);
      opacity: 0;
    }
  }
  .a{
    font-family: "sans-serif";
    src: url('src/assets/fonts/Ade-Display.otf')  format('opentype');
  }
  .b{
    font-family: "sans-serif";
    src: url('src/assets/fonts/Ade-Display.otf')  format('opentype');
  }
  </style>