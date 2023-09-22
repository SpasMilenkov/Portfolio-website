<template>
    <div class="wrapper">
        <form class="form-container" action="https://formsubmit.co/4160c5bc579f39c21948a1db62d1aa90" method="POST">
            <div class="section-wrapper">
                <input class="text-input" type="text" name="name" placeholder="John Doe" required>
                <input class="text-input" type="email" name="email" placeholder="johnDoe@example.com" required>
            </div>
            <input class="text-input" name="_subject" placeholder="Subject">
            <textarea class="text-input message" type="text" name="message" placeholder="Message"></textarea>
            <input type="hidden" name="_captcha" value="false">
            <input type="hidden" name="_next" value="https://clash2453.github.io/Portfolio-website/#contacts">
            <button class="send-button" type="submit">Send</button>
        </form>
    </div>
</template>

<script setup lang="ts">

</script>

<style scoped>
.wrapper {
    width: clamp(20rem, 100% 30rem);
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;

}

.form-container {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    gap: 3rem;
    background-color: var(--background-transparent);
    padding: 1rem;

    border-radius: 1rem;
}

.send-button {
    width: fit-content;
    background: var(--accent-color-40);
    color: var(--font-primary);
    font-size: 1.25rem;
    letter-spacing: 0.1rem;
    padding: 0.2rem 0.5rem;
    font-weight: 600;
    border-radius: 1rem;
    font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
}
.text-input{
    background-color: var(--background-20);
    font-size: 1.25rem;

    color: var(--font-primary);

    font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;

    padding: 0.5rem;
    border-radius: 1rem;

    resize: none;

    
}
.text-input::placeholder {
    opacity: 0.5;
}
</style>