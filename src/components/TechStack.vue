<template>
    <section class="tech-stack flex-column">
        <h1 class="section-header">Tech stack</h1>
        <div class="content-wrapper">
            <div class="frontend flex-wrapper">
                <h1 class="subtitle">Frontend</h1>
                <div class="flex-container">

                    <Icon v-for="icon in frontend" :icon="icon" width="5rem" />
                </div>
            </div>

            <div class="backend flex-wrapper">
                <h1 class="subtitle">Backend</h1>
                <div class="flex-container">
                    <Icon v-for="icon in backend" :icon="icon" width="5rem" />
                </div>
            </div>
            <div class="os flex-wrapper">
                <h1 class="subtitle">Operating systems</h1>
                <div class="flex-container">
                    <Icon v-for="icon in os" :icon="icon" width="5rem" />
                </div>
            </div>
            <div class="version-control flex-wrapper">
                <h1 class="subtitle">Version control</h1>
                <div class="flex-container">
                    <Icon v-for="icon in versionControl" :icon="icon" width="5rem" />
                </div>
            </div>
            <div class="design flex-wrapper">
                <h1 class="subtitle">Design</h1>
                <div class="flex-container">
                    <Icon v-for="icon in design" :icon="icon" width="5rem" />
                </div>
            </div>
        </div>
        <div class="separator">

        </div>
    </section>
</template>

<script setup lang="ts">
import { Icon } from '@iconify/vue/dist/iconify.js';


const frontend = ['devicon:html5', 'devicon:css3', 'devicon:javascript', 'devicon:typescript', 'devicon:vuejs']
const backend = ['devicon:csharp', 'devicon:dotnetcore']
const os = ['devicon:linux', 'devicon:windows8']
const versionControl = ['devicon:git', 'devicon:github']
const design = ['devicon:figma', 'devicon:gimp']
</script>

<style scoped>
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
    background: radial-gradient(circle at 5px 5px, var(--accent-color-40) 1px, transparent 0), var(--background);
    background-size: 30px 30px;
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

.backend {
    box-shadow: rgba(122, 94, 253, 0.4) 0px 0px 0px 2px, rgba(22, 94, 253, 0.65) 0px 4px 6px -1px, rgba(22, 94, 253, 0.08) 0px 1px 0px inset;
}

.frontend {
    box-shadow: rgba(13, 246, 207, 0.4) 0px 0px 0px 2px, rgba(13, 246, 207, 0.65) 0px 4px 6px -1px, rgba(13, 246, 207, 0.08) 0px 1px 0px inset;
}

.os {
    box-shadow: rgba(13, 196, 246, 0.6) 0px 0px 0px 2px, rgba(13, 196, 246, 0.85) 0px 4px 6px -1px, rgba(13, 196, 246, 0.08) 0px 1px 0px inset;
}

.design {
    /* background: linear-gradient(90deg, #06b46d, #08d79b, rgb(13, 246, 207)); */
    box-shadow: rgba(255, 0, 92, 0.4) 0px 0px 0px 2px, rgba(255, 0, 92, 0.65) 0px 4px 6px -1px, rgba(255, 0, 92, 0.08) 0px 1px 0px inset;

}

.version-control {
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

.separator{
    background: var(--blue-color);
}
</style>