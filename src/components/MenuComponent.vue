<template>
    <div class="menu-body">
        <a v-for="(circle, index) in circles" @click.prevent.capture ref="indic" :href="'#' + circle"
            @click="smoothScroll(circle)" class="circle" :class="{ active: activeSlot == index }" :key="index"></a>
    </div>
</template>
<script setup lang='ts'>
defineProps<{
    activeSlot: number
}>()
const circles = ['welcome', 'about-me', 'frontend', 'backend', 'os', 'ver-control', 'design', 'contacts']
const smoothScroll = (id: string,) => {
    const element = document.getElementById(id);
    if (element === null)
        return

    element.scrollIntoView({ behavior: 'smooth', block: 'end', inline: 'nearest' });

}
</script>

<style scoped> 
.menu-body {
     display: flex;
     flex-direction: column;
     align-items: center;
     justify-content: center;
     padding: 1rem;
     gap: 1rem;
     background-color: var(--background-20);
     border-radius: 50px;
     box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
 }

 .circle {
     display: flex;
     align-items: center;
     justify-content: center;
     padding: 0.5rem;
     aspect-ratio: 1;

     border-radius: 50%;

     background: var(--background-30);

 }

 .active {
     background-color: var(--green-color);
 }
</style>