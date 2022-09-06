<template>
    <div class="container">
        <div class="image-container filter">
            <img rel="preload" class="contacts-image" :src="image" alt="A space ship">
        </div>
        <div class="content filter">
            <h1 class="section-header">Contacts</h1>
            <p class="contacts-text">Saw something that caught your attention? Got any suggestions on how to improve this portfolio? Or have a question? You can send me an email below!</p>
            <a href="#" v-on:click.prevent @click="toggleForm" class="circle-button">Contact me</a>
        </div>
    </div>
    <ContactsForm v-if="formActive" :formActive="formActive"></ContactsForm>
</template>

<script>
import ContactsForm from './ContactsForm.vue';
    
export default {
    data: function () {
        return {
            formActive: false,
            image: this.preload()
        };
    },
    methods: {
        toggleForm() {
            const sections = [...document.getElementsByClassName('filter')];
            sections.forEach(section=>{
                section.classList.toggle('darken')
                document.body.classList.toggle('flow-hidden')
            })
            this.formActive = !this.formActive;
        },
        preload(){
            const image = new Image();
            image.src = '/images/contacts-circle-banner.webp'
            return image.src
        }
    },
    components: { ContactsForm }
}
</script>



<style scoped>
    .container{
        height: 100%;
        min-height: 750px;
        width: calc(100% - 5rem);

        display: flex;
        align-items: center;
        justify-content: space-around;
        background-color: rgba(10,4,62,1);
        padding-left: 5rem;
        padding-bottom: 2rem;
        padding-top: 10rem;
        gap: 15rem;
    }
    .darken{
        filter: brightness(65%);
    }
    .section-header{
        padding-top: 5rem;
    }
    .contacts-image{
        width: 100%;
        border-radius: 50%;
        max-width: 410px;
        min-width: 300px;
        
    }
    .image-container{
        display: flex;
        align-items: flex-start;
        height: 100%;
        padding: 2rem;
    }
    .content{
        width: 70%;
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 5rem;
    }
    .contacts-text{
        font-size: 2rem;
        color: var(--orange);
        font-family: 'Lato', sans-serif;
        line-height: 2.2rem;
        width: 80%;
        max-width: 40rem;
        text-align: center;
        background-color: rgba(200, 136, 140, 0.2);
        padding: 3rem 2rem;
        border-radius: 10px;
    }
    .circle-button{
        width: 50%;
        max-width: 250px;
        min-width: 180px;
        height: auto;
        aspect-ratio: 1/1;
        border-radius: 50%;
        background-color: rgba(200, 136, 140, 0.2);

        display: flex;
        align-items: center;
        justify-content: center;
        
        color: var(--orange);
        font-size: 2rem;
        text-decoration: none;
        font-family: 'Lato', sans-serif;
    }
    .circle-button:hover{
        transform: scale(1.02);
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
</style>