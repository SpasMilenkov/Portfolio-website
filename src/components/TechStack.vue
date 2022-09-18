<template>
    <div class="wrapper">
        <div class="container">
            <h1 class="section-header">My tech stack</h1>
            <div class="card t-card hidden">
                <h1 class="card-title">Front end</h1>
                <div class="contents">
                    <div class="image-wrapper">
                        <img class="logo" src="/images/tech-stack-images/html.webp" alt="">
                        <img class="logo" src="/images/tech-stack-images/css.webp" alt="">
                        <img class="logo" src="/images/tech-stack-images/js.webp" alt="">
                        <img class="logo" src="/images/tech-stack-images/vue.webp" alt="">
                    </div>
                </div>
            </div>
            <div class="card t-card hidden">
                <h1 class="card-title">Back end</h1>
                <div class="contents">
                    <div class="image-wrapper">
                        <img class="logo" src="/images/tech-stack-images/c-sharp.webp" alt="C sharp logo">
                        <img class="logo" src="/images/tech-stack-images/dot-net.webp" alt="">
                    </div>
                </div>
            </div>
        </div>
        <div v-if="!mobile" class="image-container"></div>
        </div>
</template>

<script>
export default {
    data: function(){
        return{
            mobile: false
        }
    },
    methods: {
        hidePicture(){
            if(window.innerWidth <= 875)
                this.mobile = true;
            if(window.innerWidth >= 875)
                this.mobile = false;
        }
    },
    mounted() {
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.intersectionRatio > 0) {
                    entry.target.classList.add('fade-in-transition')
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

    },
    created() {
        window.addEventListener("resize", this.hidePicture);
        this.hidePicture();
    },
    destroyed() {
        window.removeEventListener("resize", this.hidePicture);
    },
}
</script>

<style scoped>
    .wrapper{
        display: flex;
        width: 100%;
        height: 100%;
        background-size: cover;
        background-repeat: no-repeat;
        background-position: center;
        text-align: center;
    }
    .container{
        width: calc(30% - 2rem);
        min-height: 100vh;
        height: 100%;
        padding: 1rem;

        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        gap: 3rem;
        background: rgb(19, 30, 59)
        
    }
    .image-container{
        width: 70%;
        height: calc(100vh + 2rem);
        background-image: url('/images/tech-stack-mountain.webp');
        background-blend-mode: darken;
        background-color: rgba(0, 0, 0, 0.3);
        background-size: cover;
        background-position: center;
    }
    .card{
        overflow: hidden;
        width: calc(90% - 2rem);
        height: calc(30% - 2rem);
        border-radius: 10px;
        padding: 0 1rem;
        padding: 2rem;

        display: flex;
        align-items: center;
        justify-content: center;
        flex-direction: column;
        gap: 3rem;
    }
    .card:hover{
        box-shadow: rgba(122, 161, 201, 0.2) 0px 54px 55px, rgba(122, 161, 201, 0.12) 0px -12px 30px, rgba(122, 161, 201, 0.12) 0px 4px 6px, rgba(122, 161, 201, 0.17) 0px 12px 13px, rgba(122, 161, 201, 0.09) 0px -3px 5px;

    }
    .logo{
        width: 5rem;
        height: auto;
        min-width: 80px;
        min-height: 80px;
    }
    .card-title{
        color: #7AA1C9;
        font-family: 'Lato', sans-serif;
        font-size: 3rem;
        font-weight: 500;
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
    @media only screen and (max-width: 875px){
        .wrapper{
            flex-direction: column;
        }
        .container{
            justify-content: center;
            width: 100%;
            height: 50%;
            min-height: fit-content;
            padding: 2rem 0;
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