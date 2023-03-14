<script>

</script>

<template>
    <header>
        <div class="responsive">
            <routerlink id="hamburger">
                <span></span>
                <span></span>
            </routerlink>
            <h1>P - W</h1>
        </div>
        <div class="desktop">
            <h1>Pauline Wahle</h1>
        </div>
    </header>
</template>

<style scoped>
@media (min-width: 200px) {
    header{
        display: block;
        position: fixed;
        width: 100vw;
        box-sizing: border-box;
        z-index: 150;
    }
    .responsive{
        display: flex; 
        align-items: center;
        justify-content: flex-start;
        margin: 0;
    }
    h1{
        
        font-size: 1.2em;
        font-style: normal;
        font-weight: 100;
        text-align: center;
        text-transform: capitalize;
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
        background-color: black;

    }
}
@media (min-width: 992px) {
    header{
        padding: 10vh 0 0 0;
    }
    h1{
        font-family: 'serif';
        font-size: 1.2em;
        font-style: normal;
        font-weight: 100;
        text-align: center;
        text-transform: capitalize;
    }
}
</style>