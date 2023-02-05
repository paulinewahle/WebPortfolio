<script>

export default{
    props:{
        links: Array,
      },
    components: {
        
    },
    mounted(){

        let mouseCursor = document.querySelector(".cursor");
        let textCursor = document.querySelector(".text-cursor");
        let blob = document.querySelector(".blob");

        window.addEventListener("mousemove", mouseFollow);
        function mouseFollow(e) {
        mouseCursor.style.left = e.clientX + "px";
        mouseCursor.style.top = e.clientY + "px";
        textCursor.style.left = e.clientX + "px";
        textCursor.style.top = e.clientY + "px";

        let rightScreen = window.screen.width/2
        let leftScreen = window.screen.width/2
        if(e.pageX < rightScreen){
            //console.log("left")
        }
        else if(e.screenX > leftScreen){
            //console.log("right")
        }
        }
       
        // this.links.addEventListener("mouseover", hoverLink);
        // function hoverLink(){
        //     console.log("in")
        // }
        console.log(this.links.length)
        this.links.forEach((link) => {
        link.addEventListener("mouseleave", () => {
            blob.style.scale = 0;
            blob.style.filter = "blur(0px)";
            mouseCursor.style.scale = 1;
            mouseCursor.style.backgroundColor = "black";
            document.getElementById("d").style.fill = "black";
            mouseCursor.style.mixBlendMode = "normal";
        });
        link.addEventListener("mouseover", () => {
            blob.style.scale = 8;
            blob.style.filter = "blur(1px)";
            mouseCursor.style.backgroundColor = "white";
            document.getElementById("d").style.fill = "white";
            mouseCursor.style.mixBlendMode = "difference";
        });
        });
    },
    // methods: {
    // function (){
    //     
    // }
    
    // },
    // methods: {
    //     hover: function(){
    //         this.links.addEventListener("mouseleave", () => {
    //         console.log("out")
    //     });
    //     this.links.addEventListener("mouseover", () => {
    //         console.log("in")
    //     });
    //     }

    // }
    // data(){
    //     return{
    //         links: [],
    //     }
    // },

 
    // methods: {
    //     linkIN: function(){
    //         console.log("hi");
    //         blob.style.scale = 8;
    //         blob.style.filter = "blur(1px)";
    //         mouseCursor.style.mixBlendMode = "difference";
    //     },
    //     linkOUT: function(){
    //         link.addEventListener("mouseleave", () => {
    //         blob.style.scale = 0;
    //         blob.style.filter = "blur(0px)";
    //         mouseCursor.style.scale = 1;
    //         mouseCursor.style.mixBlendMode = "difference";
    //     });
    //     }, 
    // }
    
    // }
}
</script>


<template>
    <div class="text-cursor">
        <span>Next</span>
    </div>
    <div class="cursor">
        <svg class="blob" viewBox="0 0 800 500" preserveAspectRatio="none" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" width="100%" id="blobSvg">
            <path id="d" fill="black"> 
            <animate attributeName="d"  dur="4000ms" repeatCount="indefinite" values="
            M432,307Q364,364,307,427.5Q250,491,214.5,406Q179,321,161.5,285.5Q144,250,148,201Q152,152,201,138Q250,124,293,144Q336,164,418,207Q500,250,432,307Z;
            M443.5,327Q404,404,327,449.5Q250,495,177.5,445Q105,395,95.5,322.5Q86,250,128.5,210.5Q171,171,210.5,121.5Q250,72,300.5,110.5Q351,149,417,199.5Q483,250,443.5,327Z;
            M392.5,314.5Q379,379,314.5,394.5Q250,410,186.5,393.5Q123,377,116.5,313.5Q110,250,103,173Q96,96,173,73Q250,50,323,77Q396,104,401,177Q406,250,392.5,314.5Z;                                                    
            M394.5,309Q368,368,309,361Q250,354,178,374Q106,394,115,322Q124,250,112.5,175.5Q101,101,175.5,81Q250,61,297.5,108Q345,155,383,202.5Q421,250,394.5,309Z;
            M432,307Q364,364,307,427.5Q250,491,214.5,406Q179,321,161.5,285.5Q144,250,148,201Q152,152,201,138Q250,124,293,144Q336,164,418,207Q500,250,432,307Z
                                                                ">
            </animate>
            </path>
        </svg>
    </div>

    
        

</template>


<style scoped>

    .cursor {
        left: 0;
        top: 0;
        width: 30px;
        height: 30px;
        margin-top: -15px;
        margin-left: -15px;
        pointer-events: none;
        border-radius: 50%;
        display: flex;
        justify-content: center;
        background-color: black;
        border-radius: 50%;
        filter: blur(7px);  
        transition: scale 0.3s ease-in-out;
        position: fixed;
        z-index: 1000;
        display: flex;
        justify-content: center;
        align-items: center;
        pointer-events: none; 
    }

    .blob{
        position: absolute;

        margin-left: 50px; 
        transform: scale(1, 1);
        transform-origin: center center;
        filter: blur(7px);  
        transition: all 0.3s ease-in-out;
        transition-property: scale, filter, transform;
    }
  
    .text-cursor{
        display: none;
        height: 70px;
        width: 70px;
        margin-top: -10px;
        margin-left: -15px;
        font-size: 1em;
        filter: blur(0px);
        position: fixed;
        transition:  all .1s ease-in-out;
        z-index: 1001;
        pointer-events: none;
        
    }
    span{
        color: #eeeeee;
    }

</style>