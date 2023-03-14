<script>
export default {
    data(){
        navActive: false
    },
    methods:{
        responsiveNav(){
            if(this.navActive === false){
                this.navActive = true
                document.querySelector("#responsive-nav").style.left = "-20vw"
                document.querySelector(".nav-content").style.left = "10vw"
                document.querySelector("#header-title").style.color = "white"
                const hamburger = document.getElementById("hamburger").children;
                hamburger[0].style.backgroundColor = "white";
                hamburger[1].style.backgroundColor = "white";
                hamburger[2].style.backgroundColor = "white";
                hamburger[0].style.transform = "rotate(45deg)";
                hamburger[1].style.width = "0";
                hamburger[2].style.transform = "rotate(-45deg)";
                hamburger[0].style.marginTop = "-.6em";
                hamburger[2].style.marginTop = "1em";
                
            }
            else{
                this.navActive = false
                document.querySelector("#responsive-nav").style.left = "-150vw";
                document.querySelector(".nav-content").style.left = "-150vw";
                document.querySelector("#header-title").style.color = "#292929"
                const hamburger = document.getElementById("hamburger").children;
                hamburger[0].style.backgroundColor = "#292929";
                hamburger[1].style.backgroundColor = "#292929";
                hamburger[2].style.backgroundColor = "#292929";
                hamburger[0].style.transform = "rotate(0deg)";
                hamburger[1].style.width = "100%";
                hamburger[2].style.transform = "rotate(0deg)";
                hamburger[0].style.marginTop = "0";
                hamburger[2].style.marginTop = "0";
            }
        }
    }
}
</script>

<template>
    <header class="responsive">
        <div>
            <div id="hamburger" @click="responsiveNav()">
                <span />
                <span />
                <span />
            </div>
            <h1 id="header-title">P - W</h1>
        </div>
    </header>
    <header class="desktop">    
        <div>
            <h1>Pauline Wahle</h1>
        </div>
    </header>

    <div id="responsive-nav" class="responsive">
    </div>
    <div class="nav-content responsive">
        <div>
            <RouterLink class="small-nav-link" to="/work"> LinkedIn </RouterLink>
            <RouterLink class="small-nav-link" to="/work"> Behance </RouterLink>
            <RouterLink class="small-nav-link" to="/work"> Github </RouterLink>
            <RouterLink class="small-nav-link" to="/work"> CodePen </RouterLink>
        </div>
        <div>
            <RouterLink class="big-nav-link" to="/work"> WORK </RouterLink>
            <RouterLink class="big-nav-link" to="/work"> ABOUT </RouterLink>
        </div>
        <div>
            <p>Get in touch</p>
            <a class="small-nav-link" to="/work"> pauline.wahle@web.de </a>
        </div>
    </div>
    
</template>

<style scoped>
@media (min-width: 200px) {
    header{
        position: fixed;
        width: 100vw;
        box-sizing: border-box;
        z-index: 150;
    }
    h1{
        font-size: 1.2em;
        font-style: normal;
        font-weight: 100;
        text-align: center;
        text-transform: capitalize;
        z-index: 100000;
    }
    #hamburger{
        width: 3em;
        height: 2em;
        margin: 0 10% 0 0;
        display: flex;
        flex-direction: column;
        justify-content: space-around;
    }
    span{
        height: 2px; 
        width: 100%;
        background-color: #292929;
        transition: transform .5s ease;
        transform-origin: top left;
    }
    #responsive-nav{
        background-color: #292929;        
        height: 100vh;
        width: 100vw;
        position: fixed;
        top: 0;
        left: -150vw;
        transition: all .5s ease;
        z-index: 140;
        filter: blur(20px);
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .nav-content{
        position: fixed;        
        top: 10vh;
        height: 80vh;
        width: 50vw;
        z-index: 160;
        left: -100vw;
        transition: all .5s ease;
        display: flex;
        flex-direction: column;
        justify-content: space-around;
    }
    .big-nav-link, .small-nav-link, p{
        display: block;
        color: white;
        text-decoration: none;
        border: none;
        text-align: center;
    }
    .big-nav-link{
        font-family: "title";
        font-weight: 100;
        font-size: 2.5em;
        margin: 10%;
    }
    .small-nav-link, p{
        font-size: 1em;
    }
}
@media (min-width: 992px) {
    header{
        padding: 10vh 0 0 0;
        width: 100vw;
        display: flex;
        justify-content: center;
    }
    h1{
        font-family: 'serif';
        font-size: 1.2em;
        font-style: normal;
        font-weight: 100;
        text-transform: capitalize;
    }
}
</style>