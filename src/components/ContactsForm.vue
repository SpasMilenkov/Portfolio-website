<template>
    <div class="wrapper">
        <h1 class="section-header">Contacts</h1>
        <label for="">
            <input class="text-input" type="text">
        </label>
        <label for="">
            <input class="text-input" type="text">
        </label>
        <label for="">
            <input class="text-input" type="text">
        </label>
        <button class="send-button">Send email</button>
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
    .wrapper{
        width: 100%;
        height: 100%;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        gap: 3rem;

        background: url('/images/the-world.jpg');
        background-color: rgba(0, 0, 0, 0.7);
        background-position: center;
        background-size: cover;
        background-blend-mode: darken;
    }
    .text-input{
        border: none;
        background-color: white;
        border-radius: 5px;
        width: 25rem;
        height: 2rem;
    }
    .send-button{
        background-color: rgb(22, 206, 142);
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