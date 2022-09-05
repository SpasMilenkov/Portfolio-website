<script>
  import WelcomeSection from './components/WelcomeSection.vue';
  import AboutMe from './components/AboutMe.vue';
  import Projects from './components/Projects.vue';
  import Contacts from './components/Contacts.vue';
import TechStack from './components/TechStack.vue';
  export default {

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
                    navBarContainer.classList.remove('nav-container')                
                    return
                }
                this.inView = true;
                this.mobileView = false;
                navBarContainer.classList.remove('container-mobile')
                navBar.classList.remove('nav-expanded')
                navBarContainer.classList.add('nav-container')
            },
            toggleMenu(){
                const navBar = document.getElementById('navBar');
                const navBarContainer = document.getElementById('navBarContainer')
                navBar.classList.toggle('nav-expanded')
                navBarContainer.classList.add('nav-container-mobile')
                this.inView = !this.inView
            }
        },
        components:{
          Navigation,
          WelcomeSection,
          AboutMe,
          Projects,
          Contacts,
          TechStack
        }
    }


</script>

<template>
  <header>
    <!-- <Navigation/> -->
    <nav class="navigation" id="navBar">
        <ul class="nav-container" id="navBarContainer">
            <li v-if="mobileView" @click="toggleMenu"><i class="fi fi-rr-menu-burger nav-menu-icon"></i></li>
            <li v-if="inView"><a class="nav-link" href="#about-me">About me</a></li>
            <li v-if="inView"><a class="nav-link" href="#stack">Tech stack</a></li>
            <li v-if="inView"><a class="nav-link" href="#projects">My projects</a></li>
            <li v-if="inView"><a class="nav-link" href="#contacts">Contacts</a></li>
        </ul>
    </nav>

  </header>
  <main>
    <WelcomeSection/>
    <div id="about-me">    
      <AboutMe/>
    </div>
    <div id="stack">
      <TechStack/>
    </div>
    <div id="projects">
      <Projects/>
    </div>
    <div id="contacts">
      <Contacts/>
    </div>
  </main>
</template>

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
  .nav-container-mobile{
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

      padding: 0.3rem;
      border-radius: 5px;
  }

  .nav-link:hover{
      background-color:rgba(255,255,255, 0.1);
      text-decoration: underline;
  }

  .nav-container{
      display: flex;
      flex-direction: row-reverse;
      align-items: center;
      justify-content: flex-start;
      gap: 2rem;
  }
  .nav-menu-icon{
      font-size: 3rem;
      color: var(--orange);
  }
</style>