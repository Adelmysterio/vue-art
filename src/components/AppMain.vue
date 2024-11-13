<script>
import AppBuildings from './AppBuildings.vue';
import AppSea from './AppSea.vue';
import AppStreet from './AppStreet.vue';

export default {
    data() {
        return {
            currentTime: '',
            currentColor: '',
        };
    },
    components: {
        AppStreet,
        AppSea,
        AppBuildings
    },
    created() {
        // Imposta il colore all'avvio
        this.updateTimeAndColor();

        // Aggiorna l'orario e il colore ogni secondo
        setInterval(this.updateTimeAndColor, 1000);
    },
    methods: {
        updateTimeAndColor() {
            // Ottieni l'ora corrente
            const now = new Date();
            const hours = now.getHours();
            const minutes = now.getMinutes().toString().padStart(2, '0');
            this.currentTime = `${hours}:${minutes}`;

            // Cambia colore in base all'orario
            if (hours >= 6 && hours < 12) {
                this.currentColor = '#FFD700'; // Giallo mattutino
            } else if (hours >= 12 && hours < 13) {
                this.currentColor = '#87CEEB'; // Azzurro pomeridiano
            } else if (hours >= 13 && hours < 14) {
                this.currentColor = '#FF8C00'; // Arancione serale
            } else {
                this.currentColor = '#2F4F4F'; // Notte (Grigio scuro)
            }
        },
    },
};
</script>

<template>
    <div :style="{ background: `linear-gradient(0deg, rgba(255,255,255,1) 0%, ${currentColor} 30%)` }" class="sky">
        <section>
            <p>{{ currentTime }}</p>
        </section>
        <AppBuildings />
    </div>
    <AppStreet />
    <AppSea />
</template>

<style lang="scss" scoped>
@use '../assets/styles/partials/variables' as *;

.sky {
    height: $skyHeight;
    position: relative;
    display: flex;
    align-items: end;
    color: white;
    text-align: center;

    section {
        position: absolute;
        top: 0;
        right: 0;
        display: flex;
        justify-content: center;
        align-items: center;
        padding: 1rem;
        height: 5vh;
        font-size: 1.2rem;
    }
}
</style>