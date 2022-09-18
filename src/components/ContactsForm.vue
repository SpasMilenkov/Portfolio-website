<template>
    <div class="wrapper">
        <form class="container" action="https://formsubmit.co/4160c5bc579f39c21948a1db62d1aa90" method="POST">
            <div class="section-wrapper">
                <input class="text-input" type="text" name="name" placeholder="Name" required>
                <input class="text-input" type="email" name="email" placeholder="Email" required>
            </div>
            <input class="text-input" name="_subject" placeholder="Subject">
            <textarea class="text-input message" type="text" name="message" placeholder="Message"></textarea>
            <input type="hidden" name="_captcha" value="false">
            <input type="hidden" name="_next" value="https://clash2453.github.io/Portfolio-website/#contacts">
            <button class="send-button" type="submit">Send</button>
        </form>
    </div>
</template>

<script>
    export default{
        data: function(){
            return{}
        },
    }
</script>

<style scoped>
    .wrapper,
    .container{
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        gap: 3rem;
        min-height: calc(586px - 3rem);
    }
    .container{
        padding: 2rem 1rem;
        border-radius: 10px;
        width: 100%;
        height: 100%;
    }
    .wrapper{
        width: 100%;
        height: 100%;

        background: url('/images/nasa_mobile.webp');
        background-color: rgba(19, 21, 29, 0.3);
        background-position: center;
        background-size: cover;
        background-blend-mode: darken;
    }
    .section-wrapper{
        display: flex;
        align-items: center;
        gap: 0.5rem;
        width: 80%;
    }
    .text-input{
        border: none;
        background-color: rgba(200, 165, 121, 0.1);
        color: rgba(210, 210, 210, 1);
        padding-top: 0.5rem;
        font-size: 1.5rem;
        height: 3.5rem;
        border-bottom: 3px solid #647bbe;
        font-family: 'Robot', sans-serif;
        width: 80%;
        height: 2rem;
    }
    .text-input:focus{
        outline: none;
        background-color: rgba(200, 200, 200, 0.2);
    }
    .message{
        height: 15rem;
        padding-top: 0;
        padding-left: 0;
        resize: none;
    }
    .send-button{
        background-color: rgb(16, 143, 99);
        color: whitesmoke;
        font-size: 1.5rem;
        font-weight: 600;
        font-family: 'Lato', sans-serif;
        padding: 0.5rem 2rem;
        border: none;
        border-radius: 5px;
    }
    @media only screen and (max-width: 650px){
        .wrapper{
            min-height: 400px;
            background: url('/images/nasa_mobile.webp');
        }
    }
    @media only screen and (max-width: 1300px){
        .section-wrapper{
            flex-direction: column;
            width: 100%;
        }
        .container{
            gap: 1rem;
        }
    }
</style>