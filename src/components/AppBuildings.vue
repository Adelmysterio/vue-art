<script>
export default {
    data() {
        return {
            buildings: [
                { id: 1, height: '12vh', width: '15vh', color: 'hsl(210, 60%, 60%)', },
                { id: 2, height: '18vh', width: '22vh', color: 'hsl(120, 60%, 60%)', over: true },
                { id: 3, height: '25vh', width: '17vh', color: 'hsl(300, 60%, 60%)', right: true },
                { id: 4, height: '30vh', width: '20vh', color: 'hsl(45, 60%, 60%)' },
                { id: 5, height: '20vh', width: '28vh', color: 'hsl(180, 60%, 60%)', right: true },
                { id: 6, height: '40vh', width: '12vh', color: 'hsl(270, 60%, 60%)' },
                { id: 7, height: '22vh', width: '30vh', color: 'hsl(90, 60%, 60%)', over: true, right:true},
                { id: 8, height: '16vh', width: '19vh', color: 'hsl(60, 60%, 60%)' },
                { id: 9, height: '20vh', width: '14vh', color: 'hsl(330, 60%, 60%)' },
                { id: 10, height: '28vh', width: '30vh', color: 'hsl(15, 60%, 60%)' }
            ]
        }
    }
}
</script>

<template>
    <div v-for="item in buildings" :key="item.id">
        <div class="background"></div>
        <div class="building" :style="{ height: item.height, width: item.width, background: item.color }"
            :class="(item.over ? 'over' : ''), (item.right ? 'right' : '')"></div>
    </div>
</template>

<style lang=scss scoped>
@use '../assets/styles/partials/variables' as *;



.building {
    position: relative;
    z-index: 0;

    &.right {
        right: 5vh;
    }

    &.over {
        z-index: 1;
    }
}
</style>