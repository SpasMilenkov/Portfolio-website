<script setup>
  import WelcomeSection from './components/WelcomeSection.vue';
  import AboutMe from './components/AboutMe.vue';
  import Projects from './components/Projects.vue';
  import Navigation from './components/Navigation.vue';
</script>

<template>
  <header>
    <Navigation/>
  </header>
  <main>
    <WelcomeSection/>
    <AboutMe/>
    <Projects/>
  </main>
</template>