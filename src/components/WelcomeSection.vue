<template>
    <section class="welcome-container" :class="{ 'toggled': !toggled }">
        <div id="tiles" >
            <div class="tile" v-for="(tile, index) in tiles" :key="index" :style="{ opacity: toggled ? 0 : 1 }"
                @click="handleTileClick(index)"></div>
        </div>
        <h1 id="title" class="centered" :style="{ opacity: toggled ? 0 : 1 }">
                👋 I am
            <span class="fancy" >Spas Milenkov.</span>
        </h1>
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
        delay: anime.stagger(50, {
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
            var(--g3),
            var(--g1    ));

    background-size: 200%;
    height: 100vh;
    overflow: hidden;
    margin: 0px;
}

.welcome-container.toggled {
    animation: background-pan 10s linear infinite;
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
}

.tile {
    cursor: pointer;
    position: relative;
}

.tile:hover:before {
    background-color: rgb(30, 30, 30);
}

.tile:before {
    background-color: rgba(15, 15, 15,0.9);
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
</style>