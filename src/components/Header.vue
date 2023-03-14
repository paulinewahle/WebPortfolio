<script>

</script>

<template>
    <header>
        <div class="responsive">
            <div id="hamburger">
                <span></span>
                <span></span>
            </div>
            <h1>Pauline Wahle</h1>
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
        padding: 10vh 0 0 0;
        box-sizing: border-box;
        z-index: 150;
        border: 1px solid;
        height: 10vh;
    }
    .responsive{
        display: flex; 
        align-items: center;
        justify-content: flex-start;
        margin: 0;
        border: 1px solid blue;
    }
    h1{
        font-family: 'serif';
        font-size: 1.2em;
        font-style: normal;
        font-weight: 100;
        text-align: center;
        text-transform: capitalize;
    }
    #hamburger{
        border: 1px solid;
        width: 5px;
        height: 5px;
    }
}
@media (min-width: 992px) {

    h1{
        font-family: 'sans-serif';
        font-size: 1.2em;
        font-style: normal;
        font-weight: 100;
        text-align: center;
        text-transform: capitalize;
    }
}
</style>