<template>
    <section class="my-projects">        
        <h1 class="section-header">My projects</h1>
        <div class="container">
            <Project class="hidden"
                v-for="(project, i) in projectList"
                :key="i"
                :project="project"
            />
        </div>
    </section>
</template>

<script>
    import json from '../projectList.json'
    import Project from './Project.vue';

    export default {
    data: function () {
        return {
            projectList: json,
            project: {},
            showAble: false
        };
    },
    methods:{
            livePreview(path){
                if(path === 'false') return false
                return true
            }
        },
        mounted(){
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry =>{
                    if(entry.intersectionRatio > 0){
                        entry.target.classList.add('fade-up')
                        entry.target.classList.remove('hidden')
                        observer.unobserve(entry.target)
                    }
                })
            },{
                rootMargin: '-100px'
            })
            const projects = [...document.getElementsByClassName('project-card')]
            projects.forEach(element => {
                observer.observe(element)
            });
        },
    components: { Project }
}
</script>

<style scoped>
    .my-projects{
        width: 100% ;
        background: linear-gradient(0deg, rgba(10,4,62,1) 70%, rgba(0,0,0,1) 100%);
        display: flex;
        flex-direction: column;
        gap: 2rem;
        padding-top: 100px;
    }
    .container{
        overflow: hidden;
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        justify-content: center;

        gap: 2rem;
        padding: 1rem;

    }
    .section-header{
        text-align: center;
    }
</style>