<script setup>
import {ref} from "vue";
import Fade from "./components/Fade.vue";

</script>

<template>
    <Transition>
        <Fade :delay="500" :is-fade="true" :on="1000">
            <img src="./assets/icons/heart.svg" alt="" width="40">
        </Fade>
    </Transition>

    <Transition>
        <Fade :delay="1800">
            <div class="address">
                Чемальский тракт, <span style="font-family: Roboto, serif;">4</span> км
            </div>
        </Fade>
    </Transition>

    <Transition>
        <Fade :delay="2800">
            <div class="title">
                Пора<br>веселиться
            </div>
        </Fade>
    </Transition>


    <div class="names-time-container">
        <Transition>
            <Fade :delay="4000">
                <div class="names">
                    Артабас & Карина<br>женятся
                </div>
            </Fade>
        </Transition>

        <Transition>
            <Fade :delay="4800">
                <div class="time">
                    20 августа 2023<br>в 15:00
                </div>
            </Fade>
        </Transition>
    </div>

</template>

<style scoped>
img, .address {
    position: absolute;
    top: 10%;
    right: 10%;
}

.title {
    position: absolute;
    top: 30%;
    left: 10%;
    text-transform: uppercase;
    font-size: 40px;
}

.names-time-container {
    position: absolute;
    top: 60%;
    left: 10%;
    font-size: 25px;
}

.v-enter-active,
.v-leave-active {
    transition: opacity 1s ease;
    animation: 1s blur;
    color: transparent;
}

.v-enter-from,
.v-leave-to {
    opacity: 0;
}
</style>
