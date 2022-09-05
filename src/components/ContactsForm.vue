<template>
    <div class="wrapper" v-if="formActive" >
        <div class="contacts-form-image" ></div>
        <div class="contacts">
            <div class="top-row">
                <h1 class="section-header">Contacts</h1>
                <i class="fi fi-br-cross icon" @click="closeForm" ></i>
            </div>
            <div class="link-wrapper">
                <a class="link" href="" v-on:click.prevent="copyURL">
                <i v-if="!copied" class="fi fi-rr-envelope icon"></i>
                <i v-if="copied" class="fi fi-br-check icon"></i>
            </a>
            <a class="link" href="https://github.com/Clash2453">
                <i class="fi fi-brands-linkedin icon"></i>
            </a>
            </div>
        </div>
    </div>
</template>

<script>
    export default{
        props: ['formActive'],
        data: function(){
            return{
                copied: false
            }
        },
        methods: {
            closeForm() {
                this.$parent.toggleForm();
            },
            async copyURL() {
                try {
                    await navigator.clipboard.writeText('spasmilenkov2453@gmail.com');
                    this.copied = true;
                } catch ($e) {
                    console.log('Cannot copy');
                }
            }
            
        }
    }
</script>

<style scoped>
    .wrapper{
        min-height: 600px;
        min-width: 320px;
        max-width: 1000px;
        width: 95%;
        display: flex;
        flex-direction: row;
        gap: 3px;
        z-index: 100;
        position: fixed;
        position: fixed;
        top: 25%;
        left: 50%;
        transform: translateX(-50%);
        background-color: aquamarine;
    }
    .contacts-form-image{
        background: url(/images/contacts-banner.webp);
        background-size: cover;
        background-position: center;
        background-repeat: no-repeat;

        width: 50%;
        min-height: 300px;
    }
    .contacts{
        width: 50%;
        background-color: #2A2B3A;

        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: space-between;
    }
    .top-row{
        display: flex;
        width: calc(100% - 1rem);
        justify-content: space-between;
        align-items: center;
        padding: 0.5rem;
    }
    .link-wrapper{
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        height: 300%;

    }
    .icon{
        font-size: 2rem;
        text-decoration: none;
    }
    .fi-br-cross{
        padding-top: 0.5rem;
        font-size: 2.5rem;
        color: rgb(199, 45, 78);
    }
    @media only screen and (max-width: 650px){
        .wrapper{
            min-height: 400px;
        }
        .section-header{
            font-size: 2rem;
        }
        .fi-br-cross{
            padding-top: 0.5rem;
            font-size: 1.5rem;
        }
    }
</style>