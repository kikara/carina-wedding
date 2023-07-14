<script setup>
import {ref} from "vue";
import {onMounted} from "vue";

const text = ref(null);

onMounted(() => {
    const str = '20 августа 2023';

    for (let i = 0; i < str.length; i++) {
        let span = document.createElement("span");
        span.innerHTML = str[i];
        span.style.transform = `rotate(${10 * i}deg)`;
        text.value.appendChild(span);
    }
});




</script>

<template>
    <div class="logo-position-container">
        <div class="logo-container">
            <div class="left-letter letter">
                <span>A</span>
            </div>
            <div class="right-letter letter">
                <span>K</span>
            </div>
        </div>
    </div>
    <div class="rotate-text-box">
        <p id="text" ref="text"></p>
    </div>
</template>

<style scoped>

.logo-position-container {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    display: flex;
    align-items: center;
    justify-content: center;

    font-family: Narziss, serif;

    color: var(--base-color);
}

.logo-container {
    width: 220px;
    display: grid;
    grid-template-columns: 1fr 1fr;
    position: relative;
}

.logo-container:after {
    width: 4px;
    content: '';
    background: var(--base-color);
    position: absolute;
    left: calc(50% - 2px);

    top: 0;
    bottom: 0;

    animation: 1s line;
}

.letter {
    font-size: 100px;
    text-align: center;
    display: inline-block;
    overflow: hidden;

}

.letter span {

}

.left-letter span {
    margin-left: 100%;
    animation: 1s leftmove 1s 1 linear normal forwards;
}

.right-letter {
    position: relative;
}

.right-letter span {
    margin-left: -200%;
    animation: 1s rightmove 1s 1 linear normal forwards;
}


@keyframes leftmove {
    from {
        margin-left: 200px;
    }
    to {
        margin-left: 0;
    }
}

@keyframes rightmove {
    from {
        margin-left: -200px;
    }
    to {
        margin-left: 0;
    }
}

@keyframes line {
    from {
        top: 50%;
        bottom: 50%;
    }
    to {
        top: 0;
        bottom: 0;
    }
}

.rotate-text-box {
    position: absolute;
    top: 0;
    bottom: 0;
    left: 50%;
    width: 100%;

    display: flex;
    align-items: center;

    overflow: hidden;
}

#text {
    color: var(--base-color);
    text-transform: uppercase;
    font-size: 28px;
    font-weight: bold;
    position: relative;
    height: 300px;
    width: 300px;

    transform: rotate(180deg);
    animation: 1s rotate-text 2s 1 linear forwards;
    transform-origin: center left;
}

@keyframes rotate-text {
    from {
        transform: rotate(180deg);
    }
    to {
        transform: rotate(360deg);
    }
}



</style>