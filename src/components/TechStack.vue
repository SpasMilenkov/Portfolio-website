<template>
    <section class="tech-stack flex-column">
        <h1 class="section-header">Tech stack</h1>
        <div class="content-wrapper">
            <div class="languages flex-wrapper">
                <h1 class="subtitle">Languages</h1>
            </div>
            <div class="frameworks flex-wrapper">
                <h1 class="subtitle">Frameworks</h1>
            </div>
            <div class="os-tools flex-wrapper">
                <h1 class="subtitle">Operation systems and tools</h1>
            </div>
        </div>
    </section>      
</template>

<script setup lang="ts">    
</script>

<style scoped>
@keyframes background-pan {
    from {
        background-position: 0% center;
    }

    to {
        background-position: -200% center;
    }
}
.flex-column,
.content-wrapper {
    display: flex;
    align-items: center;
    flex-direction: column;
    justify-content: center;
    gap: 4vw;
    
}
.tech-stack {
    width: 100vw;
    min-height: 100vh;
    height: fit-content;
    gap: 3rem;
    justify-content: flex-start;
    padding: 2.5rem;
    background: url('/images/techstack-background.svg'), no-repeat, center var(--background);
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center;
    position: relative;

    animation: background-pan 20s inline infinite; 
}
.flex-wrapper {
    width: clamp(17rem, 35vw, 30rem);
    height: 20rem;
    background-color: var(--background-20);
    color: var(--accent-color);
    font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    border-radius: 15px;
    padding: 1rem;
    position: relative;
    transform-style: preserve-3d;
}
.section-header{
    width: 100%;
    text-align: center;
}
.content-wrapper {
    flex-wrap: wrap;
    flex: 1;
}
.flex-wrapper::before, 
.flex-wrapper::after{
  content: "";
  position: absolute;
  top: -50%;
  left: -50%;
  inset: -5px; /* control the spread */
  transform: translate(10px, 8px); /* control the offsets */
  transform: translate3d(10px, 8px, -1px); /* (X, Y, Z) */
  	filter: blur(20px);
}.languages::before,
.languages::after{
    background: linear-gradient(225deg, #f9c7ff, #9e63ff, rgba(0,35,255,1));
}
.frameworks::before{
    background: linear-gradient(90deg, #06b46d, #08d79b, #0df6cf);
}
.os-tools::before{
    background: linear-gradient(90deg, #f9bb73, #f9bb73, rgba(247,206,104,1));
}   
.subtitle{
    font-size: 1.35rem;
    width: 100%;
    text-align: center;

}
.content-wrapper {
    flex-direction: row;
}



</style>