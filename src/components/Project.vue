
<template>
    <div @mouseenter="showPreview" class="project-card">
        <div class="wrapper">
            <h1 class="project-title">{{project.name}}</h1>
            <div class="link-wrapper">
                <a class="link" :href="project.githubRepo" target="_blank">Github repo</a>
                <a 
                class="link" 
                :href="project.livePreview"
                v-if="livePreview(project.livePreview)"
                target="_blank"
                >Life Preview</a>
            </div>
        </div>
    </div>
</template>

<script setup lang="ts">
const props = defineProps(['project']);

const livePreview = (path: string) => {
    if (path === 'false') return false;
    return true;
};

const showPreview = () => {
    const picture = document.getElementById('preview') as HTMLImageElement;
    picture.src = props.project.image;
};
</script>

<style scoped>
    .project-card{
        height: 8rem;
        display: flex;
        flex-direction: column;
        align-items: center;
        width: calc(90% - 1rem);
        color: var(--accent-color);
        font-family: 'Roboto', sans-serif;
        font-size: 2rem;
        gap: 1rem;

        background-color: rgba(255, 255, 255, 0.1);
        padding: 0.5rem;
    }
    .project-card:hover{
        background-color: rgba(192, 192, 216, 0.2);
    }
    .project-title{
        width: fit-content;
        height: 100%;
        width: 100%;
        max-width: 15rem;
        display: flex;
        align-items: center;
        justify-content: flex-start;
        font-size: 1.5rem;
    }

    .wrapper{
        display: flex;
        align-items:center ;
        justify-content: center;
        gap: 1rem;
        width: calc(100% - 2rem);
        height: 100%;
    }
    .link-wrapper{
        display: flex;
        align-items: center;
        justify-content: center;
        flex-direction: column;
        width: 50%;
        height: 90%;
        gap: 1rem;
    }
    @media only screen and (max-width: 1600px){
        .project-card{
            width: 90%;
            max-width: 730px;
        }
    }
    @media only screen and (max-width: 750px){
        .project-card{
            width: calc(95% - 1rem);
            max-width: 730px;
            flex-direction: column;
            gap: 1rem;
            padding: 0.5rem;
            height: calc(50% + 1rem);
            min-height: fit-content;
        }
        .project-title{
            height: fit-content;
            widows: 50%;
        }
        .wrapper{
            max-width: 500px;
            widows: 100%;
            justify-content: space-around;
        }
    }
</style>