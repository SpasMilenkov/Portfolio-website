<template>
    <div class="wrapper">
        <h1 class="section-header">My tech stack</h1>
        <div class="container">
        <div class="card t-card hidden">
            <h1 class="card-title">Things I have experience with</h1>
            <div class="contents">
                <div class="image-wrapper">
                    <img class="logo" src="/images/tech-stack-images/c-sharp.webp" alt="C sharp logo">
                    <img class="logo" src="/images/tech-stack-images/html.webp" alt="">
                    <img class="logo" src="/images/tech-stack-images/css.webp" alt="">
                </div>
                <p class="card-text">
                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Velit impedit rerum magnam odio! Reprehenderit, aut! Ducimus aliquid expedita, eveniet dolorem vitae sint aut voluptatum maiores blanditiis voluptatem repellat sit nam?
                </p>
            </div>
        </div>
        <div class="card t-card hidden">
            <h1 class="card-title">Things I am currently learning</h1>
            <div class="contents">
                <div class="image-wrapper">
                    <img class="logo" src="/images/tech-stack-images/js.webp" alt="">
                    <img class="logo" src="/images/tech-stack-images/vue.webp" alt="">
                    <img class="logo" src="/images/tech-stack-images/dot-net.webp" alt="">
                </div>
                <p class="card-text">
                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Velit impedit rerum magnam odio! Reprehenderit, aut! Ducimus aliquid expedita, eveniet dolorem vitae sint aut voluptatum maiores blanditiis voluptatem repellat sit nam?
                </p>
            </div>
        </div>
        <div class="card t-card hidden">
            <h1 class="card-title">Lorem ipsum</h1>
            <div class="contents">
                <div class="image-wrapper">
                    <img class="logo" src="/images/tech-stack-images/blazor.webp" alt="">
                </div>
                <p class="card-text">
                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Velit impedit rerum magnam odio! Reprehenderit, aut! Ducimus aliquid expedita, eveniet dolorem vitae sint aut voluptatum maiores blanditiis voluptatem repellat sit nam?
                </p>
            </div>
        </div>
    </div>
    </div>
</template>

<script>
    export default {
        mounted() {
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.intersectionRatio > 0) {
                        console.log('HERE I AM')
                        entry.target.classList.add('fade-up')
                        entry.target.classList.remove('t-card', 'hidden')
                        observer.unobserve(entry.target)
                    }
                })
            }, {
                rootMargin: '-100px'
            })
            const cards = [...document.getElementsByClassName('card')]
            cards.forEach(element => {
                observer.observe(element)
            });

        }
    }
</script>

<style scoped>
    .wrapper{
        background-color: black;
        text-align: center;
    }
    .container{

        width: 100%;
        min-height: 100vh;
        height: 100%;
        padding: 1rem;

        display: flex;
        flex-wrap: wrap;
        align-items: center;
        justify-content: center;
        gap: 1rem;
        
    }
    .card{
        overflow: hidden;
        width: 35%;
        height: 30%;
        background-color: rgb(33, 36, 43);
        border-radius: 15px;
        padding: 2rem;

        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 1rem;
    }
    .logo{
        width: 20%;
        height: auto;
    }
    .card-title{
        color: var(--orange);
        font-family: 'Lato', sans-serif;
        font-size: 2rem;
        font-weight: 600;
    }
    .contents{
        display: flex;
        flex-direction: column;
        gap: 1rem;
    }
    .image-wrapper{
        display: flex;
        width: 100%;
        height: 100%;
        align-items: center;
        justify-content: center;
        flex-wrap: wrap;
        gap: 1.5rem;
    }

    .card-text{
        height: 100%;
        color: var(--orange);
        font-family: 'Lat', sans-serif;
        font-size: 1.5rem;
        padding: 0 1rem;
        line-height: 2rem;
    }
    @media only screen and (max-width: 850px){
        .container{
            justify-content: flex-start;
        }
        .card{
            width: calc(90% - 2rem);
            padding: 1rem;
        }
        .logo{
            width: 25%;
        }
    }
</style>