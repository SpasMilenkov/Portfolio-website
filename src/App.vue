<script>
  import WelcomeSection from './components/WelcomeSection.vue';
  import AboutMe from './components/AboutMe.vue';
  import Projects from './components/Projects.vue';
  import Navigation from './components/Navigation.vue';
  import Contacts from './components/Contacts.vue';
import TechStack from './components/TechStack.vue';
  export default {
    data: function(){
      return {

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
    <Navigation/>
  </header>
  <main>
    <WelcomeSection/>
    <AboutMe/>
    <TechStack/>
    <Projects/>
    <Contacts/>
  </main>
</template>