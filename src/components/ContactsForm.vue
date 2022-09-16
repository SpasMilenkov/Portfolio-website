<template>
    <div class="wrapper">
        <h1 class="section-header">Contacts</h1>
        <div class="container">
            <label class="input-container" for="sender">
                <input class="text-input" type="text" placeholder="John Doe...">
            </label>
            <label class="input-container" for="">
                <input class="text-input" type="text" placeholder="Title...">
            </label>
            <label class="input-container" for="">
                <input class="text-input" type="text" placeholder="Subject...">
            </label>
            <label class="input-container" for="">
                <input class="text-input" type="text" placeholder="Message...">
            </label>
            <button class="send-button">Send email</button>
        </div>
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
    }
    .container{
        background-color: #13151D;
        padding: 2rem 1rem;
        border-radius: 10px;
    }
    .wrapper{
        width: 100%;
        height: 100%;

        background: url('/images/the-world.jpg');
        background-color: rgba(0, 0, 0, 0.5);
        background-position: center;
        background-size: cover;
        background-blend-mode: darken;
    }
    .text-input{
        border: none;
        background-color: rgba(200, 200, 200, 0.1);
        color: rgba(210, 210, 210, 1);
        padding-top: 0.5rem;
        font-size: 1.5rem;
        height: 3.5rem;
        border-bottom: 3px solid rgb(16, 143, 99);
        font-family: 'Robot', sans-serif;
        width: 25rem;
        height: 2rem;
    }
    .text-input:focus{
        outline: none;
        background-color: rgba(200, 200, 200, 0.3);
    }
    .send-button{
        background-color: rgb(16, 143, 99);
        color: whitesmoke;
        font-size: 1.5rem;
        font-weight: 600;
        font-family: 'Lato', sans-serif;
        padding: 1rem;
        border: none;
        border-radius: 5px;
    }
    @media only screen and (max-width: 650px){
        .wrapper{
            min-height: 400px;
        }
        .section-header{
            font-size: 2rem;
        }
    }
</style>