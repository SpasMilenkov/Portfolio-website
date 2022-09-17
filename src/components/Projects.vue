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
        <div v-if="!mobile" class="preview-container">
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
            showAble: false,
            mobile: false,
        };
    },
    methods: {
        //show the live preview button if it is available
        livePreview(path) {
            if (path === 'false') return false
            return true
        },
        hidePreview(){
            if(window.innerWidth <= 1275)
                this.mobile = true;
            if(window.innerWidth >= 1275)
                this.mobile = false;
        }
    },
    //add animations as user scrolls
    mounted() {
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.intersectionRatio > 0) {
                    entry.target.classList.add('fade-up')
                    entry.target.classList.remove('hidden')
                    observer.unobserve(entry.target)
                }
            })
        }, {
            rootMargin: '-100px'
        })
        const projects = [...document.getElementsByClassName('project-card')]
        projects.forEach(element => {
            observer.observe(element)
        });
    },
    created() {
        window.addEventListener("resize", this.hidePreview);
    },
    destroyed() {
        window.removeEventListener("resize", this.hidePreview);
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
    background-color: rgb(20, 18, 29);
}
#preview{
    width: 80%;
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
@media only screen and (max-width: 1275px) {
    #preview {
        width: 95%;
        height: auto;
    }

    .preview-container {
        width: 0%;
        height: 0%;
    }
    .project-container{
        width: 100%;
    }
    .container{
        min-height: fit-content;
    }
    .my-projects{
        height: fit-content;
    }
}
</style>