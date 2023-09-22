<template>
    <main>
        <div id="welcome" class="section">
            <WelcomeSection />
        </div>
        <MenuComponent class="arrow" :active-slot="currentSection" />
        <div id="about-me" class="section">
            <AboutMe />
        </div>
        <div id="stack" class="section">
            <TechStack />
        </div>
        <div id="contacts" class="section">
            <Contacts />
        </div>
    </main>
</template>


<script setup lang="ts">
import WelcomeSection from './components/WelcomeSection.vue';
import AboutMe from './components/AboutMe.vue';
import Contacts from './components/Contacts.vue';
import TechStack from './components/skillsetComponents/TechStack.vue';
import MenuComponent from './components/MenuComponent.vue';
import { onMounted, ref } from 'vue'

const currentSection = ref(0)
const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry) => {
        if (entry.intersectionRatio > 0) {
            switch (entry.target.id) {
                case 'welcome':
                    currentSection.value = 0;
                    break
                case 'about-me':
                    currentSection.value = 1;
                    console.log(currentSection.value)
                    break
                case 'stack':
                    currentSection.value = 2;
                    break
                case 'contacts':
                    currentSection.value = 3;
                    break

            }
            console.log(currentSection.value)
        }
    });
}, {
    rootMargin: '-150px',
});
onMounted(() => {
    const sections = [...document.getElementsByClassName('section')];
    sections.forEach((element) => {
        observer.observe(element);
    });
})



</script>


<style scoped>
#projects {
    min-height: fit-content;
}

.arrow {
    position: fixed;
    bottom: 45%;
    right: 2.5rem;
    z-index: 999;
}
</style>