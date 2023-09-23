<template>
    <section class="container">
        <div class="form-container">
            <ContactsForm />
        </div>
        <div class="links-container">
            <h1 class="subtitle">Contact me on social media</h1>
            <p class="message">If you have any questions, opinions about some of my work, suggestions or offers, feel free
                to contact me via email or on social media. If not hope you at least enjoyed the website!</p>
            <div class="flex">
                <a  href="https://bg.linkedin.com/in/spas-milenkov-89a172279 ">
                    <Icon class="icon" icon="bi:linkedin" width="2.5rem" />
                </a>
                <a  href="https://github.com/Clash2453">
                    <Icon class='icon' icon="bi:github" width="2.5rem"/>
                </a>
            </div>
        </div>
    </section>
</template>

<script setup lang="ts">
import ContactsForm from './ContactsForm.vue';

</script>



<style scoped>
.container {
    display: flex;
    align-items: center;
    justify-content: space-between;

    width: 100%;
    min-height: 100vh;
    height: 100%;
    background: radial-gradient(circle at 5px 5px, var(--accent-color-40) 1px, transparent 0), var(--background);
    background-size: 30px 30px;

    padding: 0 0 0 5vw;
}

.links-container {
    display: flex;
    justify-content: center;
    flex-direction: column;
    background-color: var(--blue-color);
    width: clamp(20rem, 100%, 37.4rem);
    height: 100%;
    min-height: 100vh;
    padding: 1rem;
    gap: 2rem;
}

.subtitle {
    font-size: 2rem;
    font-weight: 700;
    letter-spacing: 0.05rem;
    text-align: left;
}

.message {
    color: var(--font-primary);
    font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    font-size: 1.2rem;
}

.flex {
    display: flex;
    align-items: center;
    gap: 1rem;
    width: clamp(15rem, 100%, 20rem);
    color: var(--accent-color-95);
}

.icon:hover {
    color:var(--accent-color );
}

@media (max-width: 1450px) {

    .container {
        flex-direction: column-reverse;
        gap: 1rem;
        padding: 0 0 1rem 0;
    }

    .links-container {
        width: 100%;
        min-height: 30rem;
    }
}
</style>