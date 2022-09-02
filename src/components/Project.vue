
<template>
    <div class="project-card">
        <h1 class="project-title">{{project.name}}</h1>
        <img class="project-image" :src="project.image" alt="">
        <div class="wrapper">
            <h1 class="wrapper-title">Tech Stack:</h1>
            <h2 v-for="(language, i) in project.software" class="language-title" :key="i">{{language}}</h2>
            <div class="link-wrapper">
                <a href="">project.</a>
                <a href=""></a>
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
        min-width: 300px;
        height: 500px;

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
        transform: scale(1.01);
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
        background-color: rgba(255, 222, 224, 0.2);
        width: 90%;
        align-self: center;
    }

    .wrapper{
        display: flex;
        flex-direction: column;
        gap: 1rem;
        width: 100%;
        border-radius: 5px;
        padding: 0.5rem;
    }
</style>