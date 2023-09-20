<template>
    <section class="tech-stack flex-column">
        <h1 class="section-header">Tech stack</h1>
        <div class="content-wrapper">
            <div class="languages flex-wrapper">
                <h1 class="subtitle">Languages</h1>
                <div class="flex-container">
                    <img v-for="(image, index) in languages" :src="image.src" :alt="image.alt" :key="index"
                        class="tech-image" v-once>
                </div>
            </div>
            <div class="frameworks flex-wrapper">
                <h1 class="subtitle">Frameworks</h1>
                <div class="flex-container">
                    <img v-for="(image, index) in frameworks" :src="image.src" :alt="image.alt" :key="index"
                        class="tech-image" v-once>
                </div>
            </div>
            <div class="os-tools flex-wrapper">
                <h1 class="subtitle">Operating systems and tools</h1>
                <div class="flex-container">
                    <img v-for="(image, index) in tools" :src="image.src" :alt="image.alt" :key="index"
                        class="tech-image" v-once>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup lang="ts">

const frameworks = [
    {
        src: "/images/tech-stack-images/vue.webp",
        alt: "Vue",
    },
    {
        src: "/images/tech-stack-images/asp.webp",
        alt: "ASP.net",
    },
    {
        src: "/images/tech-stack-images/EFCore.webp",
        alt: "EntityFramework"
    },
]
const languages = [

    {
        src: "/images/tech-stack-images/html.webp",
        alt: "CSS"
    }, {
        src: "/images/tech-stack-images/css.webp",
        alt: "HTML"
    }, {
        src: "/images/tech-stack-images/js.webp",
        alt: "JavaScript"
    }, {
        src: "/images/tech-stack-images/ts.webp",
        alt: "TypeScript"
    },
    {
        src: "/images/tech-stack-images/c-sharp.webp",
        alt: "C#"
    },
]
const tools = [
    {
        src: "/images/tech-stack-images/linux.webp",
        alt: "Linux"
    },
    {
        src: "/images/tech-stack-images/windows.webp",
        alt: "Windows"
    },
    {
        src: "/images/tech-stack-images/git.webp",
        alt: "git"
    },

]
</script>

<style scoped>
@keyframes background-pan {
    from {
        background-position: 0% center;
    }

    to {
        background-position: -200% center;
    }
}

.flex-column,
.content-wrapper,
.flex-container {
    display: flex;
    align-items: center;
    flex-direction: column;
    justify-content: center;
    gap: 4vw;
    min-height: fit-content;
}

.flex-container {
    flex-direction: row;
    flex-wrap: wrap;
    padding: 1rem;
    gap: 2rem;
    width: 100%;
    height: 100%;
    flex: 1;
}

.tech-stack {
    width: 100%;
    min-height: 100vh;
    height: fit-content;
    gap: 3rem;
    justify-content: flex-start;
    padding: 2.5rem;
    background: url('/images/techstack-background.svg'), no-repeat, center var(--background);
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center;
    position: relative;

    animation: background-pan 20s inline infinite;
}

.flex-wrapper {
    width: clamp(17rem, 35vw, 30rem);
    height: 20rem;
    min-height: fit-content;
    background-color: var(--background-20);
    color: var(--accent-color);
    font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    border-radius: 15px;
    padding: 1rem;
    position: relative;
    transform-style: preserve-3d;
}

.section-header {
    width: 100%;
    text-align: center;
}

.content-wrapper {
    flex-wrap: wrap;
    flex: 1;
}

.flex-wrapper::before,
.flex-wrapper::after {
    content: "";
    position: absolute;
    top: -50%;
    left: -50%;
    inset: -5px;
    /* control the spread */
    transform: translate(10px, 8px);
    /* control the offsets */
    transform: translate3d(10px, 8px, -1px);
    /* (X, Y, Z) */
    filter: blur(20px);
}

.languages {
    /* color: rgb(13, 196, 246); */
    /* background: linear-gradient(225deg, #f9c7ff, rgb(158, 99, 255), rgba(0,35,255,1)); */
    box-shadow: rgba(13, 196, 246, 0.6) 0px 0px 0px 2px, rgba(13, 196, 246, 0.85) 0px 4px 6px -1px, rgba(13, 196, 246, 0.08) 0px 1px 0px inset;

}

.frameworks {
    /* background: linear-gradient(90deg, #06b46d, #08d79b, rgb(13, 246, 207)); */
    box-shadow: rgba(13, 246, 207, 0.4) 0px 0px 0px 2px, rgba(13, 246, 207, 0.65) 0px 4px 6px -1px, rgba(13, 246, 207, 0.08) 0px 1px 0px inset;

}

.os-tools {
    /* background: linear-gradient(90deg, rgb(249, 187, 115), #f9bb73, rgba(247,206,104,1)); */
    box-shadow: rgba(249, 187, 115, 0.4) 0px 0px 0px 2px, rgba(249, 187, 115, 0.65) 0px 4px 6px -1px, rgba(249, 187, 115, 0.08) 0px 1px 0px inset;

}

.subtitle {
    font-size: 1.35rem;
    width: 100%;
    text-align: center;

}

.content-wrapper {
    flex-direction: row;
        min-height: fit-content;
}

.tech-image {
    aspect-ratio: 1;
    width: 5rem;
}
</style>