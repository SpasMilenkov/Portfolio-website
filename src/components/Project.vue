
<template>
    <div class="project-card">
        <div class="project-image-wrapper">
            <img class="project-image" :src="project.image" alt="">
        </div>
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

<script>

    export default {
        props: ['project'],
        data: function() {
            return {
            }
        },
        methods:{
            livePreview(path){
                if(path === 'false') return false
                return true
            }
        }
    }
</script>

<style scoped>
    .project-card{
        height: 50%;
        max-height: 600px;
        display: flex;
        flex-direction: column;
        align-items: center;
        width: 90%;
        max-width: 720px;
        border-radius: 5px;
        color: var(--orange);
        font-family: 'Roboto', sans-serif;
        font-size: 2rem;
        gap: 1rem;

        background-color: rgba(200, 136, 140, 0.1);
        border-radius: 10px;
        padding: 1rem;
    }
    .project-image-wrapper{
        border-radius: 10px;
        width: auto;
        max-height: 370px;
    }
    .project-image{
        width: 100%;
        height: 100%;
        border-radius: 10px;
    }
    .project-card:hover{
        background-color: rgba(255, 222, 224, 0.2);
    }
    .project-title{
        border-radius: 5px;
        background-color: rgba(255, 222, 224, 0.2);
        width: fit-content;
        padding: 0.5rem;
        height: 20%;
        display: flex;
        align-items: center;
        justify-content: center;
        font-size: 1.5rem;
    }
    .wrapper-title{
        border-radius: 5px;
        text-align: center;
        width: fit-content;
        padding: 0.5rem;
        align-self: center;
        font-size: 1.5rem;
    }

    .wrapper{
        display: flex;
        flex-direction: column;
        align-items:center ;
        justify-content: center;
        gap: 1rem;
        width: calc(100% - 2rem);
        height: fit-content;
        border-radius: 5px;
        padding: 0.5rem;
        background-color: rgba(255, 222, 224, 0.2);
    }
    .language-title{
        font-size: 1.5rem;
    }
    .tech-stack{
        padding: 0.5rem;
        text-align: center;
    }
    .link-wrapper{
        display: flex;
        align-items: center;
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
            width: 90%;
            max-width: 730px;
            flex-direction: column;
            gap: 1rem;
            padding: 1rem;
            height: calc(50% + 2rem);
        }
        .project-image-wrapper{
            width: 100%;
            height: 50%;
            max-width: 500px;
        }
        .project-image{
            border-radius: 5px;
        }
        .wrapper{
            max-width: 500px;
        }
    }
</style>