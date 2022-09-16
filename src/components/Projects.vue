<template>
    <section class="my-projects">
        <div class="project-container">
            <h1 class="section-header">My projects</h1>
            <div class="container">
                <Project class="hidden"
                    v-for="(project, i) in projectList"
                    :key="i"
                    :project="project"
                />
            </div>
        </div>
        <div class="preview-container">
            <img src="" alt="" id="preview">
        </div>        
    </section>
</template>

<script>
    //list of all projects 
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
            //show the live preview button if it is available
            livePreview(path){
                if(path === 'false') return false
                return true
            }
        },
        //add animations as user scrolls
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
.my-projects {
    width: 100%;
    background: rgb(22, 23, 59);
    height: 100vh;
    display: flex;
}

.project-container {
    width: 30%;
    background-color: rgb(19, 20, 29);
    display: flex;
    flex-direction: column;
    gap: 1rem;
    padding: 1rem 0;
}

.section-header {
    text-align: center;
    width: 90%;
    margin-left: 1rem;
}

.container {
    overflow: hidden;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 100vh;
    gap: 1rem;
    overflow: auto;
}
.preview-container{
    display: flex;
    justify-content: center;
    align-items: center;
    width: 70%;
}
#preview{
    widows: 100%;
    height: auto;
}
.container {
    scrollbar-width: normal;
    scrollbar-color: var(--orange) rgba(40, 43, 52, 0.2);
}

.container::-webkit-scrollbar {
    width: 5px;
    background-color: rgba(40, 43, 52, 0.9);
}

.container::-webkit-scrollbar-thumb {
    border-radius: 0.4vw;
    height: 30px;
    background-color: var(--orange);
}

.container::-webkit-scrollbar-thumb:hover {
    border-radius: 5px;
    height: 30px;
    background-color: var(--orange);
}

.container::-webkit-scrollbar-track {
    background-color: rgba(40, 43, 52, 0.9);
    border-radius: 5px;
}
</style>