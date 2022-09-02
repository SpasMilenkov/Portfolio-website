<script setup>
  import WelcomeSection from './components/WelcomeSection.vue';
  import AboutMe from './components/AboutMe.vue';
  import Projects from './components/Projects.vue';
  import Navigation from './components/Navigation.vue';
  import Contacts from './components/Contacts.vue';
</script>

<template>
  <header>
    <Navigation/>
  </header>
  <main>
    <WelcomeSection/>
    <AboutMe/>
    <Projects/>
    <Contacts/>
  </main>
</template>