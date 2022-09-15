<template>
    <div class="container">
        <div class="form-container">
            <ContactsForm/>
        </div>
        <div class="content">
            <h1 class="section-header">Contacts</h1>
            <p class="contacts-text">Saw something that caught your attention? Got any suggestions on how to improve this portfolio? Or have a question? Send me an email!</p>
        </div>
    </div>
</template>

<script>
import ContactsForm from './ContactsForm.vue';
    
export default {
    components: { ContactsForm }
}
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
        width: 70%;
        height: 100%;

        display: flex;
        align-items: center;
        justify-content: center;
    }
    .section-header{
        padding-top: 5rem;
    }
    .content{
        width: 30%;
        height: 100%;
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 5rem;
        background-color: #13233B;
    }
    .contacts-text{
        font-size: 2rem;
        color: var(--orange);
        font-family: 'Lato', sans-serif;
        line-height: 2.2rem;
        width: 80%;
        max-width: 40rem;
        text-align: center;
        background-color: rgba(255, 255, 255, 0.2);
        padding: 3rem 2rem;
        border-radius: 10px;
    }
    @media only screen and (max-width: 1200px){
        .container{
            flex-direction: column;
            padding-left: 0;
            width: 100%;
            gap: 0;
        }
        .contacts-text{
            font-size: 1.7rem;
        }
    }
    @media only screen and (max-width: 750px){
        .contacts-text{
            min-height: auto;
            width: 90%;
        }
    }
</style>