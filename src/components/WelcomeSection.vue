<template>
    <div id="main-container">
        <h1 class="greeting">Lorem Ipsum</h1>
    </div>
</template>

<style scoped>
    #main-container{
        max-width: 100%;
        height: calc(100vh - 90px);
        margin-top: 90px;
        background: url(./images/main-banner.jpeg);
        background-size: cover;
        background-repeat: no-repeat;
        background-position: center;
        display: flex;
        flex-direction: column;
        align-items: center;
        padding-top: 1.5rem;
    }

    .greeting{
        color: #CAA387;
        font-family: 'Roboto', sans-serif;
        font-size: 3.5rem;
        z-index: 2;
    }
    @media only screen and (max-width: 720px){
        .greeting{
            font-size: 2rem;
        }
        #main-container{
            height: calc(290px -  1rem);
            padding-bottom: 1.5rem;
        }
    }
</style>