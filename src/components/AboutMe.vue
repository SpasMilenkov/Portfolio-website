<script>
    export default {
        data: function(){
            return {
                profilePic: '/images/github-pfp.webp',
            }
        },
        methods: {
            setIcon(){
                this.profilePic = '/images/github-icon.webp'
            },
            setProfile(){
                this.profilePic = '/images/github-pfp.webp'
            }
        },
        mounted(){
            const fadeUpObserver = new IntersectionObserver((entries) => {
                entries.forEach(entry =>{
                    if(entry.intersectionRatio > 0){
                        entry.target.classList.add('fade-in-transition')
                        entry.target.classList.remove('hidden', 'insert-animation')

                        fadeUpObserver.disconnect
                    }
                })
            },{
                rootMargin: '50px'
            })
            const paragraph = [...document.getElementsByClassName('about-paragraph')]
            paragraph.forEach(element => {
                fadeUpObserver.observe(element)
            });
    }
}

</script>

<template>
    <div class="container">
        <div class="text-area">
            <h1 class="section-header">About me</h1>
            <p class="about-paragraph  hidden">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Unde nam iusto voluptatum quod, nobis veniam ipsa dolorem facere ea nisi laudantium accusamus quia cupiditate magni rerum libero eum quis suscipit!</p>
        </div>
        <div class="image-container">
            <a      

                class="git-link"  href="https://github.com/Clash2453" target="_blank"
                >
                <img 
                    @mouseenter="setIcon()"
                    @mouseleave="setProfile()"
                    @touchstart="setIcon()"
                    @touchend="setProfile()"
                    class="github-pfp" 
                    alt="My github profile picture"
                    :src="profilePic"
                >
            </a>
        </div>
    </div>
</template>



<style scoped>
    .container{
        width: 100%;
        /* min-height: calc(95vh - 2rem); */
        min-height: 100vh;
        background-color: #000000;

        display: flex;
        justify-content: center;
        align-items: center;
        gap: 1rem;
        padding-top: 2rem;
    }

    .about-paragraph{
        color: var(--orange);
        height: 50%;
        font-size: 2rem;
        line-height: 3rem;
        padding: 1rem;
        width: 90%;
        border-radius: 15px;
        background-color: rgb(33, 36, 43);
    }
    .section-header{
        width: fit-content;
        padding: 1rem;
        border-radius: 15px;
        box-shadow: none;
        z-index: 1;
    }
    .text-area{
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        gap: 2rem;
        width: 50%;
    }
    .image-container{
        display: flex;
        justify-content: flex-start;
        align-items: center;
        height: 100%;
        
    }
    .github-pfp{
        width: 90%;
        max-width: 410px;
        height: auto;
        aspect-ratio: 1/1;
        border: solid 5px var(--orange);
        border-radius: 50%;
        background-color: rgb(230, 230, 230);
    }
    .git-link{
        display:flex;
        align-items: center;
        justify-content: center;
        max-width: 410px;
        border-radius: 50%;
    }

    @media only screen and (max-width:750px){
        .container{
            flex-direction: column;
            justify-content: flex-start;
            gap: 2rem;
        }
        .about-paragraph{
            font-size: 1.5rem;
            line-height: 2rem;
            height: 100%;
        }
        .text-area{
            width: 95%;
            gap: 0.5rem;
        }
        .image-container{
            width: 90%;
            justify-content: center;
        }
        .github-pfp{
            width: 80%;
        }
        .section-header{
            font-size: 2.5rem;
        }
    }
</style>