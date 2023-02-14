<script>
export default{
    data() {
    return {
      show1: true,
      show2: false,
      show3: false,
      show4: false,
      show5: false,
      show6: false,
      show7: false,
    }
}
}
</script>

<template>
   <div id="page-numbers">
      <button @click="show2 = false; show3 = false; show4 = false; show5 = false; show6 = false; show7 = false; show1 = true;" id="page-number-1">1</button>
      <button @click="show1 = false; show3 = false; show4 = false; show5 = false; show6 = false; show7 = false; show2 = true;" id="page-number-2">2</button>
      <button @click="show1 = false; show2 = false; show4 = false; show5 = false; show6 = false; show7 = false; show3 = true;" id="page-number-3">3</button>
      <button @click="show1 = false; show2 = false; show3 = false; show5 = false; show6 = false; show7 = false; show4 = true;" id="page-number-4">4</button>
      <button @click="show1 = false; show2 = false; show3 = false; show4 = false; show6 = false; show7 = false; show5 = true;" id="page-number-5">5</button>
      <button @click="show1 = false; show2 = false; show3 = false; show4 = false; show5 = false; show7 = false; show6 = true;" id="page-number-6">6</button>
      <button @click="show1 = false; show2 = false; show3 = false; show4 = false; show5 = false; show6 = false; show7 = true;" id="page-number-7">7</button>
    </div>
</template>

<style scoped>
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
</style>