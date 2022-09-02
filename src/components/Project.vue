
<template>
    <div class="project-card">
        <h1 class="project-title">{{project.name}}</h1>
        <img class="project-image" :src="project.image" alt="">
        <div class="wrapper">
            <h1 class="wrapper-title">Tech Stack:</h1>
            <h2 v-for="(language, i) in project.software" class="language-title" :key="i">{{language}}</h2>
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
        }
    }
</script>

<style scoped>
    .project-card{
        width: 20%;
        min-width:calc(300px - 2rem) ;
        height: 750px;

        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 1rem;
        border-radius: 5px;
        color: var(--orange);
        font-family: 'Roboto', sans-serif;
        font-size: 2rem;
        padding: 1rem;

        background-color: rgba(200, 136, 140, 0.2);
    }
    .project-image{
        width: 70%;
        height: auto;
        aspect-ratio: 1/1;
        border-radius: 10px;
    }
    .project-card:hover{
        background-color: rgba(255, 222, 224, 0.2);
    }
    .project-title{
        border-radius: 5px;
        text-align: center;
        background-color: rgba(255, 222, 224, 0.2);
    }
    .wrapper-title{
        border-radius: 5px;
        text-align: center;
        width: 90%;
        align-self: center;
    }

    .wrapper{
        display: flex;
        flex-wrap: wrap;
        align-items:center ;
        justify-content: center;
        gap: 1rem;
        width: 100%;
        height: 500px;
        border-radius: 5px;
        padding: 1rem 0.5rem;
        background-color: rgba(255, 222, 224, 0.2);
    }
    .language-title{
        font-size: 1.5rem;
    }
</style>