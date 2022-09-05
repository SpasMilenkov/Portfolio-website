<template>
    <nav class="navigation" id="navBar">
        <ul class="container" id="navBarContainer">
            <li v-if="mobileView" @click="toggleMenu"><i class="fi fi-rr-menu-burger menu-icon"></i></li>
            <li v-if="inView"><a class="nav-link" href="#About-me">About me</a></li>
            <li v-if="inView"><a class="nav-link" href="#Projects">My projects</a></li>
            <li v-if="inView"><a class="nav-link" href="#Contacts">Contacts</a></li>
        </ul>
    </nav>

</template>

<script>
    export default{
        data: function(){
            return{
                inView: true,
                mobileView: false
            }
        },
        created() {
            window.addEventListener("resize", this.onResize);
            },
        destroyed() {
            window.removeEventListener("resize", this.onResize);
        },
        mounted(){
            this.onResize()
        },
        
        methods: {
            onResize(){
                const navBarContainer = document.getElementById('navBarContainer')
                const navBar = document.getElementById('navBar');
                if(window.innerWidth <= 650){
                    this.inView = false;
                    this.mobileView = true;

                    navBarContainer.classList.add('container-mobile')
                    navBarContainer.classList.remove('container')                
                    return
                }
                this.inView = true;
                this.mobileView = false;
                navBarContainer.classList.remove('container-mobile')
                navBar.classList.remove('nav-expanded')
                navBarContainer.classList.add('container')
            },
            toggleMenu(){
                const navBar = document.getElementById('navBar');
                const navBarContainer = document.getElementById('navBarContainer')
                navBar.classList.toggle('nav-expanded')
                navBarContainer.classList.add('container-mobile')
                this.inView = !this.inView
            }
        }
    }
</script>


<style scoped>
    .navigation{
        position: fixed;
        top: 0;
        height: 90px;
        width: calc(100% - 2rem);;
        background-color: rgba(0,0,0,.5);
        z-index: 999;

        display: flex;
        align-items: center;
        flex-direction: row-reverse;
        padding: 0 1rem;
    }
    .nav-expanded{
        height: fit-content;
        padding: 0 1rem;
    }
    .container-mobile{
        display: flex;
        flex-direction: column;
        align-items: flex-end;
        justify-content: flex-end;
        gap: 1rem;
        padding-top: 1rem;
    }
    .nav-link{
        color: var(--orange);
        font-family: 'Roboto', sans-serif;
        text-decoration: none;
        font-size: 20pt;

        padding: 0 0.25rem;
    }

    .nav-link:hover{
        background-color:#283d3f;
        text-decoration: underline;
    }

    .container{
        display: flex;
        flex-direction: row-reverse;
        align-items: center;
        justify-content: flex-start;
        gap: 2rem;
    }
    .menu-icon{
        font-size: 3rem;
        color: var(--orange);
    }
</style>