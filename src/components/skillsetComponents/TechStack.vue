<template>
    <section class="tech-stack flex-column">
        <h1 class="section-header">Tech stack</h1>
        <TechSection :settings="frontendSection" />
        <TechSection :settings="backendSection" />
        <TechSection :settings="osSection" />
        <TechSection :settings="versionControl" />
        <TechSection :settings="designSection" />
    </section>
</template>

<script setup lang="ts">
import TechSection from './TechSection.vue';
import { SectionSettings } from './TechSection.vue'
const frontendSection: SectionSettings = {
    title: 'Frontend',
    icons: ['devicon:html5', 'devicon:css3', 'devicon:javascript', 'devicon:typescript', 'devicon:vuejs'],
    backgroundColor: 'var(--green-color)',
    description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Totam quia ullam enim reiciendis nobis magni quod, distinctio sed culpa corrupti itaque ea nulla dolores maiores iure! Doloremque rem reprehenderit deleniti!',
    projectUrl: '',
    projectLivePreview: {
        available: true,
        url: ''
    },
    fontColor: 'var(--background-20)' 
}
const backendSection: SectionSettings = {
    title: 'Backend',
    icons: ['devicon:csharp', 'devicon:dotnetcore'],
    backgroundColor: '#51BBFE',
    description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Totam quia ullam enim reiciendis nobis magni quod, distinctio sed culpa corrupti itaque ea nulla dolores maiores iure! Doloremque rem reprehenderit deleniti!',
    projectUrl: '',
    projectLivePreview: {
        available: true,
        url: ''
    },
    fontColor: 'var(--background-20)'
}
const osSection: SectionSettings = {
    title: 'Operating Systems',
    icons: ['devicon:linux', 'devicon:windows8'],
    backgroundColor: 'var(--background)',
    description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Totam quia ullam enim reiciendis nobis magni quod, distinctio sed culpa corrupti itaque ea nulla dolores maiores iure! Doloremque rem reprehenderit deleniti!',
    projectUrl: '',
    projectLivePreview: {
        available: true,
        url: ''
    },
    fontColor: 'var(--font-primary)'
}
const versionControl: SectionSettings = {
    title: 'Version Control',
    icons: ['devicon:git', 'devicon:github'],
    backgroundColor: '#FFBA08',
    description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Totam quia ullam enim reiciendis nobis magni quod, distinctio sed culpa corrupti itaque ea nulla dolores maiores iure! Doloremque rem reprehenderit deleniti!',
    projectUrl: '',
    projectLivePreview: {
        available: true,
        url: ''
    },
    fontColor: 'var(--background-20)'
}
const designSection: SectionSettings = {
    title: 'Design',
    icons: ['devicon:figma', 'devicon:gimp'],
    backgroundColor: 'var(--g1)',
    description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Totam quia ullam enim reiciendis nobis magni quod, distinctio sed culpa corrupti itaque ea nulla dolores maiores iure! Doloremque rem reprehenderit deleniti!',
    projectUrl: '',
    projectLivePreview: {
        available: true,
        url: ''
    },
    fontColor: 'var(--font-primary)'
}  
</script>

<style scoped>
/* Styling for tech-stack */
.tech-stack {
    width: 100%;
    min-height: 100vh;
    gap: 0;
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 1rem 0 0 0;
    align-items: center;
    background: radial-gradient(circle at 5px 5px, var(--accent-color-40) 1px, transparent 0), var(--background);
    background-size: 30px 30px;
    position: relative;
    animation: background-pan 20s inline infinite;
}

/* Styling for section headers */
.section-header {
    width: 100%;
    text-align: center;
}

.section-header {
    border: 1px solid var(--blue-color);
    margin-bottom: 1rem;
}
</style>