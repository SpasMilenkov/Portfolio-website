<template>
    <section class="stack-section">
        <div class="fe-table flex-wrapper">
            <h1 class="subtitle">{{ settings.title }}</h1>
            <div class="flex-container">
                <Icon v-for="icon in settings.icons" :icon="icon" width="5rem" />
            </div>
        </div>
        <div class="info-container">
            <p class="description">{{ settings.description }}</p>
            <div class="project-container">
                <h2 class="project-title">Project Title</h2>
                <button class="project-button" v-if="settings.projectLivePreview.available">Live preview</button>
                <button class="project-button" v-if="!settings.projectLivePreview.available">Live preview</button>

            </div>
        </div>
    </section>
</template>
<script setup lang='ts'>
defineProps<{
    settings: SectionSettings
}>()


export interface SectionSettings {
    title: string,
    icons: string[],
    backgroundColor: string,
    projectUrl?: string,
    description: string,
    fontColor: string,
    projectLivePreview: {
        available: boolean,
        url: string
    }
}

</script>
<style scoped>
.stack-section {
    width: 100%;
    min-height: 40rem;

    display: flex;
    align-items: center;
    justify-content: space-between;

    padding: 1rem 7.5vw;

    background: v-bind('settings.backgroundColor');
}

.flex-container {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    justify-content: center;
    padding: 1rem;
    gap: 1rem;
    height: 100%;
    min-height: 25rem;
}

.fe-table {
    width: 20rem;
    height: 100%;
    /* flex: 1; */
    display: flex;
    flex-direction: column-reverse;
    align-items: center;
    justify-content: space-between;
}
.info-container {
    display: flex;
    flex-direction: column;
    align-items: center; 
    justify-content: flex-start;

    gap: 1rem;
}
.project-container {
    width: clamp(10rem, 100%, 30rem);
    display: flex;
    align-items: center;
    justify-content: space-between;
    background-color: var(--background-20);
    padding: 1rem;

    border-radius: 1rem;
}
.info-container {
    display: flex;
    width: clamp(20rem, 40%, 30rem);
    padding: 1rem;
}

.description,
.project-title,
.project-button {
    font-size: 1.25rem;
    font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
}
.project-title{
    color: var(--font-primary);
}
.subtitle,
.description {
    color: v-bind('settings.fontColor');
}

.subtitle {
    text-align: center;
    width: 100%;
    font-size: 2.5rem;
    font-weight: 700;
    letter-spacing: 0.1rem;
}
.project-button {
    background: var(--accent-color-40);
    color: var(--font-primary);
    font-size: 1rem;
    padding: 0.5rem;
    font-weight: 600;
    border-radius: 1rem;
}

@media (max-width: 1080px){
    .stack-section {
        flex-direction: column;
    }
}
</style>