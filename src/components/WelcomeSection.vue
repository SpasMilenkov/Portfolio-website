<template>
    <div id="main-container">
        <h1 class="greeting">Imagination is the limit, so lets imagine together.</h1>
    </div>
</template>

<style scoped>
    #main-container{
        max-width: 100%;
        height: calc(100vh - 90px);
        margin-top: 90px;
        background: url(/images/main-banner.webp), linear-gradient(0deg, rgba(0,0,0,1) 10%, rgba(89,125,140,0) 20%),radial-gradient(circle, rgba(0,0,0,0) 57%, rgba(0,0,0,1) 100%);;
        background-size: cover;
        background-repeat: no-repeat;
        background-position: center;
        background-blend-mode: darken;
        display: flex;
        flex-direction: column-reverse;
        align-items: center;
        padding-top: 1.5rem;
        animation: fade-in;
        animation-duration: 4s;
    }

    .greeting{
        color: #CAA387;
        font-family: 'Roboto', sans-serif;
        font-size: 3rem;
        z-index: 2;
        padding-bottom: 5rem;
        line-break: auto;
        widows: 90%;
        text-align: center;
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