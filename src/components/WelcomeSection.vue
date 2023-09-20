<template>
    <section class="">
        <div class="welcome-container"  >
            <div id="tiles" :class="{ 'toggled': !toggled }">
                <div class="tile" v-for="(tile, index) in tiles" :key="index" :style="{ opacity: toggled ? 0 : 1 }"
                    @click="handleTileClick(index)"></div>
            </div>
            <h1 id="title" class="centered" :style="{ opacity: toggled ? 0 : 1 }">
                👋 I am
                <span class="fancy">Spas Milenkov.</span>
            </h1>
        </div>
            <div id="back-panel" :style="{ opacity: !toggled ? 0 : 1 }">
                <h1 class="main-title">
                    Web Developer<br/>
                    CS Student
                </h1>
                <div class="status-container">
                    <div class="status-bubble"></div>
                    <h2 class="subtitle">Open to work</h2>
                </div>
            </div>  
    </section>
</template>

<script setup lang="ts">
import { ref, onMounted, onBeforeUnmount } from 'vue';
import anime from 'animejs';

const toggled = ref(true);
const tiles = ref<number[]>([]);
let columns = ref(0);
let rows = ref(0);

const toggle = () => {
    toggled.value = !toggled.value;
};


const handleTileClick = (index: number) => {
    toggle();

    anime({
        targets: '.tile',
        opacity: toggled.value ? 0 : 1,
        delay: anime.stagger(65, {
            grid: [columns.value, rows.value],
            from: index,
        }),
    }); 

};

const createGrid = () => {
    tiles.value = [];
    toggled.value = !toggled.value
    const size = window.innerWidth > 800 ? 80 : 50;
    columns.value = Math.floor(window.innerWidth / size);
    rows.value = Math.floor(window.innerHeight / size);

    for (let i = 0; i < columns.value * rows.value; i++) {
        tiles.value.push(i);
    }
};

onMounted(() => {
    createGrid();
    window.addEventListener('resize', createGrid);
});

onBeforeUnmount(() => {
    window.removeEventListener('resize', createGrid);
});
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

.welcome-container {
    animation: none;
    background: linear-gradient(to right,
            var(--g1),
            var(--g2),
            var(--g1));
    height: 100vh;
    transition: opacity 700ms ease;
    overflow: hidden;
    margin: 0px;
}


.welcome-container.toggled>#tiles>.tile:hover {
    opacity: 1 !important;
}

.centered {
    left: 50%;
    position: absolute;
    top: 50%;
    transform: translate(-50%, -50%);
}

#tiles {
    height: calc(100vh - 1px);
    width: calc(100vw - 1px);
    position: relative;
    z-index: 2;

    display: grid;
    grid-template-columns: repeat(v-bind('columns'), 1fr);
    grid-template-rows: repeat(v-bind('rows'), 1fr);
    transition: opacity 2000ms ease;
    opacity: 0;
}
#tiles.toggled {
    background: linear-gradient(to right,
            var(--g1),
            var(--g2),
            var(--g1));
    background-size: 200%;
    animation: background-pan 10s linear infinite;
    opacity: 1;
}
.tile {
    cursor: pointer;
    position: relative;
}

.tile:hover:before {
    background-color: rgb(30, 30, 30);
}

.tile:before {
    background-color: rgba(15, 15, 15, 0.95);
    content: "";
    inset: 0.5px;
    position: absolute;
}

#title {
    color: white;
    font-family: "Rubik", sans-serif;
    font-size: 6vw;
    margin: 0px;
    pointer-events: none;
    transition: opacity 1200ms ease;
    width: 50vw;
    z-index: 3;
}

#title>.fancy {
    color: var(--g2);
    font-family: 'Dancing Script', cursive;
    font-size: 1.2em;
    line-height: 0.9em;
}

#back-panel {
    position: absolute;
    height: 100%;
    width: 100%;
    background: radial-gradient(circle at 5px 5px, var(--accent-color-40) 1px, transparent 0), var(--background);
    background-size: 30px 30px;
    z-index: 1;
    top: 0;
    left: 0;
    transition: opacity 500ms ease;
    opacity: 0.56 ;
    color: var(--font-primary);

    display: flex;
    align-items: center;
    padding: 5vw;

}
#back-panel.toggled {
    opacity: 0;
}
.main-title {
    font-size: 5.5vw;
    font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    font-weight: 800;
    letter-spacing: 0.5rem;
    line-height: 150%;
}
.status-container {
    padding: 0.5rem;
    border-radius: 1rem;
    background: var(--background-20);
    display: flex;
    align-items: center;
    gap: 0.5rem;

    position: absolute;
    bottom: 3rem;
    right: 2rem;

    box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
    border: solid 2px var(--green-color);
}
.status-bubble {
    width: 1.5rem;
    height: 1.5rem;
    background-color: var(--green-color); 
    border-radius: 50%;
}

</style>