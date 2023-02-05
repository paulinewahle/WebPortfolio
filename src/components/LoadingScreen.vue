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

      if (id>=5){
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
          Design Concepts
        </li>
        <li class="intro-loop-item" id="intro-loop-item2">
          Web Development
        </li>
        <li class="intro-loop-item" id="intro-loop-item3">
          Creative Content
        </li>
        <li class="intro-loop-item" id="intro-loop-item4">
          Usability Strategy
        </li>
        <li class="intro-loop-item" id="intro-loop-item5">
          Digital Experience
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
  </style>