<template>
    <section class="tech-stack flex-column">
        <h1 class="section-header">Tech stack</h1>
        <TechSection class="section" id="frontend" :settings="frontendSection" />
        <TechSection class="section" id="backend" :settings="backendSection" />
        <TechSection class="section" id="os" :settings="osSection" />
        <TechSection class="section" id="ver-control" :settings="versionControl" />
        <TechSection class="section" id="design" :settings="designSection" />
    </section>
</template>

<script setup lang="ts">
import TechSection from './TechSection.vue';
import { SectionSettings } from './TechSection.vue'
const frontendSection: SectionSettings = {
    title: 'Frontend',
    icons: ['devicon:html5', 'devicon:css3', 'devicon:javascript', 'devicon:typescript', 'devicon:vuejs'],
    backgroundColor: 'var(--green-color)',
    description: "I've accumulated some valuable experience in crafting websites and web applications.I've worked with technologies like Vue, HTML, CSS, JavaScript, and TypeScript. Throughout my journey, I've developed websites that strike a balance between aesthetics and functionality.",
    projectUrl: '',
    projectTitle: 'Restaurant Page',
    projectLivePreview: {
        available: true,
        url: 'https://clash2453.github.io/Restaurant-Page/'
    },
    fontColor: 'var(--background-20)',
    hasProject: true
}
const backendSection: SectionSettings = {
    title: 'Backend',
    icons: ['devicon:csharp', 'devicon:dotnetcore'],
    backgroundColor: '#4169e1',
    description: "I've gained valuable experience in backend development, with a focus on C#, ASP.NET, and Entity Framework. Over time, I've designed backend systems that effectively manage data and handle complex business processes.I'm confident in my ability to utilize C#, ASP.NET, and Entity Framework to develop reliable backend solutions.",
    projectUrl: 'https://github.com/Clash2453/School-Management-System',
    projectTitle: 'School Management System',
    projectLivePreview: {
        available: false,
    },
    fontColor: 'var(--font-primary)',
    hasProject: true
}
const osSection: SectionSettings = {
    title: 'Operating Systems',
    icons: ['devicon:linux', 'devicon:windows8'],
    backgroundColor: 'var(--background)',
    description: "I am proficient in working on both Linux and Windows environments, and can easily handle tasks ranging from system administration to software development.",
    projectUrl: '',
    projectLivePreview: {
        available: true,
        url: ''
    },
    fontColor: 'var(--font-primary)',
    hasProject: false
}
const versionControl: SectionSettings = {
    title: 'Version Control',
    icons: ['devicon:git', 'devicon:github'],
    backgroundColor: '#FFBA08',
    description: 'Over the last two years, I have gained extensive experience using Git and Git Hub for managing versions of my projects. As a result, I can confidently say that Git has become an integral part of my development workflow.',
    projectUrl: '',
    projectLivePreview: {
        available: true,
        url: ''
    },
    fontColor: 'var(--background-20)',
    hasProject: false
}
const designSection: SectionSettings = {
    title: 'Design',
    icons: ['devicon:figma', 'devicon:gimp'],
    backgroundColor: 'var(--g1)',
    description: 'When it comes to web design, I have experience using tools like Figma to create beautiful, responsive, and functional UI/UX solutions.',
    projectUrl: '',
    projectLivePreview: {
        available: true,
        url: ''
    },
    fontColor: 'var(--font-primary)',
    hasProject: false
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