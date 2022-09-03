
<template>
    <div class="project-card">
        <div class="project-image-wrapper">
        <img class="project-image" :src="project.image" alt=""></div>
        <div class="wrapper">
            <h1 class="project-title">{{project.name}}</h1>
            <p class="tech-stack">
                <span class="wrapper-title">Tech Stack:</span><br> <span v-for="(language, i) in project.software" class="language-title" :key="i"> {{' ' + language}}</span>
            </p>
            <div class="link-wrapper">
                <a class="link" :href="project.githubRepo">Github repo</a>
                <a 
                class="link" 
                :href="project.livePreview"
                v-if="project.livePreview ? false : true"
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

        }
    }
</script>

<style scoped>
    .project-card{
        height: 400px;
        width: 45%;
        display: flex;
        align-items: center;
        border-radius: 5px;
        color: var(--orange);
        font-family: 'Roboto', sans-serif;
        font-size: 2rem;

        background-color: rgba(200, 136, 140, 0.2);
        border-radius: 10px;
    }
    .project-image-wrapper{
        border-radius: 10px;
        width: 200%;
        height: 100%;
    }
    .project-image{
        width: 100%;
        height: 100%;
        border-top-left-radius: 10px;
        border-bottom-left-radius: 10px;
    }
    .project-card:hover{
        background-color: rgba(255, 222, 224, 0.2);
    }
    .project-title{
        border-radius: 5px;
        background-color: rgba(255, 222, 224, 0.2);
        width: 100%;
        height: 20%;
        display: flex;
        align-items: center;
        justify-content: center;
        font-size: 1.5rem;
    }
    .wrapper-title{
        border-radius: 5px;
        text-align: center;
        width: 100%;
        align-self: center;
        font-size: 1.5rem;
    }

    .wrapper{
        display: flex;
        flex-wrap: wrap;
        align-items:center ;
        justify-content: center;
        gap: 1rem;
        width: 100%;
        height:calc(400px - 1rem) ;
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