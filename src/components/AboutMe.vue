<script setup lang="ts">
import { Icon } from '@iconify/vue/dist/iconify.js';
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
    <section class="container">
        <div class="text-area">
            <h1 class="section-header hidden about-animation">About me</h1>
            <p class="about-paragraph  hidden about-animation"> Hi, my name is Spas Milenkov. A 20-year-old Computer and
                Software Science student at Technical University Sofia. I am a passionate web developer and tech
                enthusiast.</p>
        </div>
        <div class="snippets">
            <img src="https://avatars.githubusercontent.com/u/87969078?v=4" alt="" class="picture">

            <div class="snippets-container">
                <div class="snippet-body">
                    <div class="circle-blue"></div>
                    <h2 class="subtitle">Graduated School for Foreign Languages Bertolt Brecht in the city of Pazardzhik,
                        Bulgaria</h2>
                </div>

                <div class="snippet-body">
                    <div class="circle-blue"></div>
                    <h2 class="subtitle">Currently studying "Informatics and Software Science" at Technical University Sofia
                    </h2>
                </div>
            </div>
        </div>
        <div class="separator"></div>
    </section>
</template>

<style scoped>


.container {
    width: 100%;
    min-height: 100vh;
    background: radial-gradient(circle at 5px 5px, var(--g2) 1px, transparent 0), var(--background);
    background-size: 30px 30px;
    position: relative;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 5vw 7.5vw 5vw 5vw;
}

.about-paragraph {
    color: var(--font-primary);
    background: var(--background-transparent);
    font-family: 'Lato', sans-serif;
    height: 50%;
    font-size: 1.25rem;
    line-height: 2.5rem;
    padding: 1rem;
    width: clamp(17rem, 50vw, 20rem);

    border-radius: 1rem;
    border: solid 1px var(--g2);
}

.section-header {
    width: fit-content;
    border-radius: 15px;
    width: 80%;
    box-shadow: none;
    z-index: 1;
    border: solid 1px var(--g2);
}

.text-area {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    gap: 2rem;
    width: 30%;
}

.snippets-container,
.snippets {
    width: fit-content;

    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    gap: 2rem;
}

.snippets {
    background: var(--background-transparent);
    padding: 3rem;
    border-radius: 1rem;
    border: 1px solid var(--g2);
    width: clamp(20rem, 100%, 30rem);
}

.snippet-body {
    background: var(--background-20);
    padding: 1rem;
    border-radius: 1rem;
    min-height: 7rem;

    max-width: 25rem;
    display: flex;
    align-items: center;
    justify-content: center;

    gap: 1rem;
}

.picture {
    border-radius: 50%;
    width: clamp(15rem, 15vw, 20rem);
    content: "";
}

.subtitle {
    font-size: 1rem;
}

.circle-blue {
    width: 2.5rem;
    aspect-ratio: 1;
    background: var(--blue-color);
    border-radius: 50%;
}

.separator {
    background: var(--g2);
}

@media only screen and (max-width:750px) {
    .container {
        flex-direction: column;
        justify-content: flex-start;
        gap: 2rem;
        padding: 2rem 0;

    }

    .about-paragraph {
        font-size: 1.5rem;
        line-height: 2rem;
        height: 100%;
        width: 100%;
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
    .snippet-body {
        padding: 0;
    }
    .subtitle {
        word-wrap: break-word;
        white-space: none;
    }
    .section-header {
        font-size: 2.5rem;
    }
    .snippets{
        padding: 1rem;
    }
}</style>