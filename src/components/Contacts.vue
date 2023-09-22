<template>
    <section class="container">
        <div class="form-container">
            <ContactsForm />
        </div>
        <div class="links-container">
            <h1 class="subtitle">Contact me on social media</h1>
            <div class="flex">
                <a href="">
                    <Icon icon="bi:linkedin" width="1.7rem" />
                </a>
                <a href="">
                    <Icon icon="bi:github" width="1.7rem" />
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
    background: radial-gradient(circle at 5px 5px, var(--accent-color-40) 1px, transparent 0), var(--background);
    background-size: 30px 30px;

    padding: 0 0 0 5vw;
}

.links-container {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    background-color: var(--g2);
    width: clamp(20rem, 100%, 37.4rem);
    height: 100%;
    min-height: 100vh;
}

.subtitle {
    font-size: 2rem;
    font-weight: 700;
    letter-spacing: 0.05rem;
}
.flex {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 1rem;
    width: 100%;
    color: var(--accent-color-95);
}
</style>