<template>
    <div class="container">
        <div class="form-container">
            <ContactsForm/>
        </div>
        <div class="content">
            <h1 class="section-header">Contacts</h1>
            <p class="contacts-text">Saw something that got your attention? Got any suggestions on how to improve this portfolio? Or have a question? Send me an email!</p>
        </div>
    </div>
</template>

<script setup lang="ts">
import ContactsForm from './ContactsForm.vue';
    
</script>



<style scoped>
    .container{
        height: 100vh;
        width: 100%;

        display: flex;
        align-items: center;
        justify-content: space-around;
    }
    .form-container{
        width: 60%;
        height: 100%;

        display: flex;
        align-items: center;
        justify-content: center;
    }
    .content{
        width: 40%;
        min-height: calc(586px - 3rem);
        height: 100%;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        gap: 5rem;
        background-color: #10151E;
    }
    .contacts-text{
        font-size: 1.8rem;
        color: var(--accent-color);;
        font-family: 'Lato', sans-serif;
        line-height: 2.2rem;
        width: 70%;
        max-width: 40rem;
        text-align: left;
        background-color: rgba(81, 99, 153, 0.2);
        padding: 2rem 1rem ;
        border-radius: 10px;
    }
    @media only screen and (max-width: 950px){
        .container{
            flex-direction: column-reverse;
            height: fit-content;
            padding-left: 0;
            width: 100%;
            gap: 0;
        }
        .contacts-text{
            font-size: 1.7rem;
            width: 100%;
        }
        .content{
            width: 100%;
        }
        .form-container{
            width: 100%;
        }
        .content{
            padding-top: 1rem;
            gap: 3rem;
            min-height: fit-content;
            padding-bottom: 3rem;
        }
    }
    @media only screen and (max-width: 750px){
        .contacts-text{
            min-height: auto;
            width: 90%;
        }
    }
</style>