<template>
    <section id="my-projects">        
        <h1 class="section-header">My projects</h1>
        <div class="container">
            <Project
                v-for="(project, i) in projectList"
                :key="i"
                :project="project"
            />
        </div>
    </section>
</template>

<script>
    import json from '../../public/projectList.json'
    import Project from './Project.vue';

    export default {
    data: function () {
        return {
            projectList: json,
            project: {}
        };
    },
    methods: {},
    components: { Project }
}
</script>

<style scoped>
    #my-projects{
        width: 100% ;
        background: linear-gradient(0deg, rgba(10,4,62,1) 70%, rgba(0,0,0,1) 100%);
        display: flex;
        flex-direction: column;
        gap: 2rem;
    }
    .container{
        overflow: hidden;
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        justify-content: center;

        gap: 1rem;
        padding: 1rem;

    }
    .section-header{
        text-align: center;
    }
</style>