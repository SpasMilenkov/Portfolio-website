<template>
    <section class="container">
        <div class="form-container">
            <ContactsForm />
        </div>
        <div class="content">
            <h1 class="section-header">Contacts</h1>
            <p class="contacts-text">Saw something that got your attention? Got any suggestions on how to improve this
                portfolio? Or have a question? Send me an email!</p>
        </div>
    </section>
</template>

<script setup lang="ts">
import ContactsForm from './ContactsForm.vue';

</script>



<style scoped>
.container {
    display: flex;
    width: 100%;
    min-height: 100vh;
    background: radial-gradient(circle at 5px 5px, var(--accent-color-40) 1px, transparent 0), var(--background);
    background-size: 30px 30px;
}
</style>