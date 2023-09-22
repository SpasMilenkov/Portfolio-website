<template>
    <div class="wrapper">
        <form class="form-container" action="https://formsubmit.co/4160c5bc579f39c21948a1db62d1aa90" method="POST">
            <div class="section-wrapper">
                <label for="" class="input-label">
                    Name:
                    <input class="text-input" type="text" name="name" placeholder="John Doe" required>

                </label>
                <label for="" class="input-label">
                    Email:
                    <input class="text-input" type="email" name="email" placeholder="johnDoe@example.com" required>

                </label>
            </div>

            <label for="" class="input-label">
                Subject:
                <input class="text-input" name="_subject" placeholder="My awesome subject">

            </label>
            <label for="" class="input-label">
                Message:
                <textarea id="message-input" class="text-input message" type="text" name="message"
                    placeholder="I kind of liked this website, could have been worse!"></textarea>

            </label>
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
    border: solid 1px var(--g2);
    border-radius: 1rem;
}

.send-button {
    width: fit-content;
    background: var(--accent-color-40);
    color: var(--font-primary);
    font-size: 1.5rem;
    letter-spacing: 0.1rem;
    padding: 0.2rem 0.5rem;
    font-weight: 600;
    border-radius: 1rem;
    font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    align-self: flex-end;
}

.section-wrapper {
    display: flex;
    align-items: center;
    gap: 1rem;
}

.text-input,
.input-label {
    width: 100%;
    font-size: 1.25rem;

    color: var(--font-primary);

    font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;

    padding: 0.5rem;
    border-radius: 1rem;

    resize: none;
}
.text-input {
    background-color: var(--background-20);

}
.input-label {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
}
#message-input,
.section-wrapper {
    width: clamp(17rem, 100%, 40rem);
}

#message-input {
    min-height: 15rem;
}

.text-input::placeholder {
    opacity: 0.5;
}

</style>