<template>
    <div id="main-container">
        <div class="container">
            <h1 class="greeting">Hi my name's Spas</h1>
            <p class="short-text">A passionate computer science student and aspiring frontend developer.</p>
        </div>
        <div class="image-container"></div>
    </div>
</template>

<style scoped>
    #main-container{
        max-width: 100%;
        height: 100vh;
        display: flex;
        align-items: center;
    }
    .container{
        width: 30%;
        height: 100%;
        background-color: #13233B;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        gap: 25%;
    }
    .image-container{
        width: 70%;
        height: 100vh;
        background: url("/images/mountain2.jpg");
        background-color: rgba(0, 0, 0, 0.2);
        background-size: cover;
        background-repeat: no-repeat;
        background-position: center;
        background-blend-mode: darken;
    }
    .short-text{
        font-size: 1.5rem;
        font-family: 'Lato', sans-serif;
        color: #C0C0D8;
        width: 80%;
        text-align: left;
        line-height: 2rem;
    }
    .greeting{
        color: #CAA387;
        font-family: 'Roboto', sans-serif;
        font-size: 3rem;
        z-index: 2;
        line-break: auto;
        width: 80%;
    }
    @media only screen and (max-width: 720px){
        .greeting{
            font-size: 1.5rem;
            padding-bottom: 0;
        }
        #main-container{
            height: calc(290px -  1rem);
            padding-bottom: 1.5rem;
            background: url(/images/main-banner-mobile.webp), linear-gradient(0deg, rgba(0,0,0,1) 10%, rgba(89,125,140,0) 20%);
            background-position: center;
            background-size: cover;
        }
    }
</style>