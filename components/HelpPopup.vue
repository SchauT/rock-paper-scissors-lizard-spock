<template>
    <div class="blur-screen">
        <div class="help-card">
            <h1 class="rules-title">RULES</h1>
            <img class="image-rules" src="~/assets/image-rules.svg">
            <img class="icon-close" @click="$emit('closeHelp')" src="~/assets/icon-close.svg">
        </div>
    </div>
</template>

<script>
export default {

}
</script>

<style scoped>
.blur-screen {
    width: 100%;
    height: 100%;

    position: absolute;
    top: 0;
    bottom: 0;
    right: 0;
    left: 0;

    background: rgba(0, 0, 0, .65);
    background-blend-mode: darken;
    backdrop-filter: blur(3px);

    display: flex;
    justify-content: center;
    align-items: center;
}
.help-card {
    width: 100%;
    height: 100%;
    background-color: white;

    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    align-items: center;
}
.rules-title {
    color: hsl(229, 25%, 31%);
}

@media only screen and (min-width: 576px) {
    .help-card {
        width: 400px;
        height: 500px;
        border-radius: 5%;
    }
    .icon-close {
        position: absolute;
        top: calc(50% - 225px);
        right: calc(50% - 180px);
    }
}
</style>