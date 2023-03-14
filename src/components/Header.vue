<script>

</script>

<template>
    <header>
        <div class="responsive">
            <h1>Pauline Wahle</h1>
        </div>
        <div class="desktop">
            <h1>Pauline Wahle</h1>
        </div>
    </header>
</template>

<style scoped>
@media (max-width: 992px) {
    header{
        display: block;
        position: fixed;
        width: 40%;
        box-sizing: border-box;
        z-index: 150;
        border: 1px solid;
        margin: 0;
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
@media (min-width: 992px) {
    header{
        display: block;
        position: fixed;
        width: 100vw;
        padding: 10vh 0 0 0;
        box-sizing: border-box;
        z-index: 150;
        display: flex;
        justify-content: center;
    }
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