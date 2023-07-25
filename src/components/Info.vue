<script setup>
import {onMounted, ref} from "vue";

const info = ref(false);
const invitation = ref(false);
const names = ref(false);
const date = ref(false);

onMounted(() => {
    setTimeout(() => info.value = true, 500);
    setTimeout(() => invitation.value = true, 1200);
    setTimeout(() => names.value = true, 1800);
    setTimeout(() => date.value = true, 2200);
});

</script>

<template>
    <Transition>
        <div class="info-container" v-if="info">
            <div class="logo-container">
                <div class="right-letter letter">A</div>
                <div class="left-letter letter">K</div>
            </div>
        </div>
    </Transition>

    <Transition>
        <div class="invitation" v-if="invitation">Приглашение</div>
    </Transition>

    <Transition>
        <div class="names-container" v-if="names">
            <div class="names">
                <div class="joiner">Той</div>
                <div class=""></div>
            </div>
        </div>
    </Transition>

    <Transition>
        <div class="footer" v-if="date">
            <div class="date">20/08/2023</div>
            <div>
                <div class="time">15:00</div>
                <div class="">
                    Чемальский тракт 4км, <br> Экспугим Парк
                </div>
            </div>
        </div>
    </Transition>

</template>

<style scoped>
.info-container {
    display: flex;
    justify-content: center;
    font-size: 50px;
    margin-top: 30px;
    font-family: Narziss, serif;
}

.logo-container:after {
    content: '';
    position: absolute;

    top: 5%;
    bottom: 5%;
    left: 50%;

    width: 3px;
    background: var(--base-color);
}

.letter {
    padding-right: 7px;
    padding-left: 7px;
}

.right-letter {
    text-align: end;
}

.left-letter {
    text-align: start;
}

.invitation {
    text-align: center;
    margin-top: 2rem;
    font-size: 30px;
    text-transform: uppercase;
    //font-family: Tenor, serif;
}

.names-container {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    min-height: 100vh;
    display: flex;
    align-items: center;
}

.names {
    font-weight: bold;
    font-size: 50px;
    text-align: center;
    text-transform: uppercase;
    width: 100%;
}

.joiner {
    position: relative;
}

.joiner:after {
    content: '';
    position: absolute;
    top: 50%;
    left: 70%;
    right: 0;
    height: 2px;
    background: var(--base-color);
}

.joiner:before {
    content: '';
    position: absolute;
    top: 50%;
    left: 0;
    right: 70%;
    height: 2px;
    background: var(--base-color);
}

.v-enter-active,
.v-leave-active {
    transition: opacity 1s ease;
    animation: 1s blur;
    color: transparent;
}

@keyframes blur {
    from {
        text-shadow: 0 0 8px #000000;
    }
    to {
        text-shadow: 0 0 0 var(--base-color);
    }
}

.v-enter-from,
.v-leave-to {
    opacity: 0;
}

.footer {
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    text-align: center;
    margin-bottom: 2rem;
    font-size: 20px;
}

.footer div {
    margin-top: .5rem;
}

.date,.time {
    font-family: Allison, cursive;
    font-weight: bold;
}

.date {
    font-size: 40px;
}

.time {
    font-size: 35px;
}
</style>