<script setup>
import {onMounted, ref} from "vue";

const props = defineProps({
    delay: Number,
    on: Number,
    isFade: {
        type: Boolean,
        default: false,
    },
});


const show = ref(false);

onMounted(() => {
    setTimeout(() => show.value = true, props.delay);
    if (props.isFade) {
        setTimeout(() => show.value = false, props.delay + props.on);
    }
});


</script>

<template>
    <div v-if="show">
        <slot></slot>
    </div>
</template>

<style scoped>

</style>