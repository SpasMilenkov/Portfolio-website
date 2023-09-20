<script setup lang="ts">
import { onMounted } from 'vue'

onMounted(() => {
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
            <p class="about-paragraph  hidden about-animation"> Hi, my name is Spas Milenkov. A 20-year-old Computer and
                Software Science student at Technical University Sofia. I am a passionate web developer and tech
                enthusiast.</p>
        </div>
        <div class="snippets-container">

            <div class="snippet-body">
                <div class="circle-blue"></div>
                <h2 class="subtitle">Graduated School for Foreign Languages Bertolt Brecht in the city of Pazardzhik, Bulgaria</h2>
            </div>

            <div class="snippet-body">
                <div class="circle-blue"></div>
                <h2 class="subtitle">Currently studying "Informatics and Software Science" at Technical University Sofia</h2>
            </div>
            
        </div>
    </div>
</template>



<style scoped>
.container {
    width: 100%;
    height: 100vh;
    background: radial-gradient(circle at 5px 5px, var(--accent-color-40) 1px, transparent 0), var(--background);
    background-size: 30px 30px;
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
}

.about-paragraph {
    color: var(--font-primary);
    font-family: 'Lato', sans-serif;
    height: 50%;
    font-size: 1.5rem;
    line-height: 3rem;
    padding: 1rem;
    width: clamp(15rem, 50vw, 20);
    border-radius: 15px;
}

.section-header {
    width: fit-content;
    border-radius: 15px;
    width: 80%;
    box-shadow: none;
    z-index: 1;
}

.text-area {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    gap: 2rem;
    width: 30%;
}

.snippets-container {
    height: 100vh;
    width: 60%;

    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    gap: 5rem;
}

.snippet-body{
    background: var(--background-20);
    padding: 1rem;
    border-radius: 1rem;

    width: 25rem;
    display: flex;
    align-items: center;
    justify-content: center;

    gap: 1rem;
}
.subtitle{
    font-size: 1rem;
}

.circle-blue{
    width: 2.5rem;
    aspect-ratio: 1;
    background: var(--blue-color);
    border-radius: 50%;
}

@media only screen and (max-width:750px) {
    .container {
        flex-direction: column;
        justify-content: flex-start;
        gap: 2rem;
        padding-top: 2rem;
    }

    .about-paragraph {
        font-size: 1.5rem;
        line-height: 2rem;
        height: 100%;
    }

    .text-area {
        width: 95%;
        height: 50%;
        gap: 0.5rem;
    }

    .snippets-container {
        width: 100%;
        justify-content: center;
    }

    .section-header {
        font-size: 2.5rem;
    }
}
</style>