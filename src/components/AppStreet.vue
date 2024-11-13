<script>
export default {
    data() {
        return {

        }
    }
}
</script>

<template>
    <div class="street">

    </div>
</template>

<style lang=scss scoped>
@use '../assets/styles/partials/variables' as *;

div.street {
    background-color: gray;
    height: $streetHeight;

    .building {
        position: relative;
        margin-right: 1vh;
    }
}
</style>