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
        }
    }
</script>

<template>
    <div class="container">
        <div class="text-area">
            <h1 class="section-header">About me</h1>
            <p class="about-paragraph">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Unde nam iusto voluptatum quod, nobis veniam ipsa dolorem facere ea nisi laudantium accusamus quia cupiditate magni rerum libero eum quis suscipit!</p>
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
        min-height: calc(95vh - 2rem);
        background-color: #000000;

        display: flex;
        justify-content: center;
        align-items: center;
        gap: 1rem;
        padding-top: 2rem;
    }

    .about-paragraph{
        color: var(--orange);
        width: 30%;
        height: 50%;
        font-size: 2rem;
        line-height: 3rem;
        width: 90%;
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