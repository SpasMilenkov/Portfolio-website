<template>
    <nav class="navigation">
        <ul class="container">
            <li><a class="nav-link" href="#About-me">About me</a></li>
            <li><a class="nav-link" href="#Projects">My projects</a></li>
            <li><a class="nav-link" href="#Contacts">Contacts</a></li>
        </ul>
    </nav>

</template>

<style scoped>
    .navigation{
        position: fixed;
        top: 0;
        height: 90px;
        width: calc(100% - 2rem);;
        background-color: rgba(0,0,0,.5);
        z-index: 999;

        display: flex;
        align-items: center;
        flex-direction: row-reverse;
        padding: 0 1rem;
    }
    .nav-link{
        color: var(--orange);
        font-family: 'Roboto', sans-serif;
        text-decoration: none;
        font-size: 20pt;

        padding: 0 0.25rem;
    }

    .nav-link:hover{
        background-color:#283d3f;
        text-decoration: underline;
    }

    .container{
        display: flex;
        flex-direction: row-reverse;
        align-items: center;
        justify-content: flex-start;
        gap: 2rem;
    }
</style>