<script setup>
  import NavigationVue from './components/Navigation.vue';
  import WelcomeSection from './components/WelcomeSection.vue';
  import AboutMe from './components/AboutMe.vue';
  import Projects from './components/Projects.vue';
</script>

<template>
  <header>
    <NavigationVue></NavigationVue>
  </header>
  <main>
    <WelcomeSection></WelcomeSection>
    <AboutMe></AboutMe>
    <Projects></Projects>
  </main>
</template>