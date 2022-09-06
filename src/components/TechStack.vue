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
                    I picked up programming as a hobby in early 2019 when I taught myself the basics of web development, HTML, and CSS. I kept doing programming as a hobby until last year when I studied the C and C# programming languages at university.
                </p>
            </div>
        </div>
        <div class="card t-card hidden">
            <h1 class="card-title">Things I am currently learning</h1>
            <div class="contents">
                <div class="image-wrapper">
                    <img class="logo" src="/images/tech-stack-images/js.webp" alt="">
                    <img class="logo" src="/images/tech-stack-images/vue.webp" alt="">
                </div>
                <p class="card-text">
                    Over the last few months, confident in my problem-solving capabilities, I have been creating projects with JavaScript and recently picked up the Vue JS framework.
                </p>
            </div>
        </div>
        <div class="card t-card hidden">
            <h1 class="card-title">Lorem ipsum</h1>
            <div class="contents">
                <div class="image-wrapper">
                    <img class="logo" src="/images/tech-stack-images/blazor.webp" alt="">
                    <img class="logo" src="/images/tech-stack-images/dot-net.webp" alt="">
                </div>
                <p class="card-text">
                    In the future, I am looking forward to diving deeper into the backend parts of web development. Check out the Blazor and .NET frameworks and create full-stack web applications.
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
        padding-top: 100px;
        background-color: black;
        text-align: center;
    }
    .container{

        width: calc(100% - 2rem);
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
        font-family: 'Lato', sans-serif;
        font-size: 1.5rem;
        padding: 0 1rem;
        line-height: 2rem;
        min-height: 260px;

        display: flex;
        text-align:center;
        align-items: center;
    }
    @media only screen and (max-width: 875px){
        .container{
            justify-content: center;
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