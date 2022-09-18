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
        background: url("/images/mountain-main.webp");
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
        #main-container{
            flex-direction: column;
        }
        .greeting{
            font-size: 2rem;
            padding-bottom: 0;
        }
        .short-text{
            font-size: 1.3rem;
        }
        .container{
            width: 100%;
            min-height: fit-content;
            gap: 2rem;
            padding: 2rem 0;
        }
        .image-container{
            width: 100%;
            min-height: 50vh;
        }
    }
</style>