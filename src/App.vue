<script setup>
import LogoEffect from "./components/LogoEffect.vue";
import {ref} from "vue";
import Info from "./components/Info.vue";

const showLogo = ref(true);

setTimeout(() => showLogo.value = false, 3300);

</script>

<template>
    <Transition name="logo">
        <LogoEffect v-if="showLogo"></LogoEffect>
    </Transition>

    <Info v-if="!showLogo"></Info>
</template>

<style scoped>
.logo-enter-active,
.logo-leave-active {
    transition: opacity 0.5s ease;
}
.logo-enter-from,
.logo-leave-to {
    opacity: 0;
}
</style>
