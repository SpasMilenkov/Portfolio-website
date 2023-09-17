<script setup lang="ts">
import {onMounted} from 'vue'

onMounted( ()=> {
    const fadeUpObserver = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
            if (entry.intersectionRatio > 0) {
                entry.target.classList.add('fade-in-transition')
                entry.target.classList.remove('hidden', 'about-animation')

                fadeUpObserver.disconnect
            }
        })
    }, {
    })
    const paragraph = [...document.getElementsByClassName('about-animation')]
    paragraph.forEach(element => {
        fadeUpObserver.observe(element)
    });
})
</script>

<template>
    <div class="container">
        <div class="text-area">
            <h1 class="section-header hidden about-animation">About me</h1>
            <p class="about-paragraph  hidden about-animation"> Hi, my name is Spas Milenkov. A 20-year-old Computer and Software Science student at Technical University Sofia. I aspire to become a passionate web developer, tech enthusiast, and big fan of the night sky.</p>
        </div>
        <div class="image-container"></div>
    </div>
</template>



<style scoped>
    .container{
        width: 100%;
        min-height: 100vh;
        background-color: #13151D;

        display: flex;
        justify-content: center;
        align-items: center;
    }

    .about-paragraph{
        color: var(--font-primary);
        font-family: 'Lato', sans-serif;
        height: 50%;
        font-size: 2rem;
        line-height: 3rem;
        padding: 1rem;
        width: 80%;
        border-radius: 15px;
    }
    .section-header{
        width: fit-content;
        border-radius: 15px;
        width: 80%;
        box-shadow: none;
        z-index: 1;
    }
    .text-area{
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: center;
        gap: 2rem;
        width: 30%;
    }
    .image-container{
        background: url("/images/sofia.webp");
        background-color: rgba(0, 0, 0, 0.2);
        background-size: cover;
        background-repeat: no-repeat;
        background-position: center;
        background-blend-mode: darken;
        height: 100vh;
        width: 70%;
    }
    @media only screen and (max-width:750px){
        .container{
            flex-direction: column;
            justify-content: flex-start;
            gap: 2rem;
            padding-top: 2rem;
        }
        .about-paragraph{
            font-size: 1.5rem;
            line-height: 2rem;
            height: 100%;
        }
        .text-area{
            width: 95%;
            height: 50%;
            gap: 0.5rem;
        }
        .image-container{
            width: 100%;
            justify-content: center;
        }
        .section-header{
            font-size: 2.5rem;
        }
    }
</style>