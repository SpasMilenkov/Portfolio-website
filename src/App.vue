<script>
import WelcomeSection from './components/WelcomeSection.vue';
import AboutMe from './components/AboutMe.vue';
import Projects from './components/Projects.vue';
import Contacts from './components/Contacts.vue';
import TechStack from './components/TechStack.vue';
export default {
    components: {
        WelcomeSection,
        AboutMe,
        Projects,
        TechStack,
        Contacts
    }
}
</script>

<template>
    <main>
        <WelcomeSection />
        <div id="about-me">
            <AboutMe />
        </div>
        <div id="stack">
            <TechStack />
        </div>
        <div id="projects">
            <Projects />
        </div>
        <div id="contacts">
            <Contacts />
        </div>
    </main>
</template>
<style scoped>
#projects {
    min-height: fit-content;
}
</style>