<script setup lang="ts">
import { ref, computed, useSlots } from 'vue';

const isOpen = ref(false);
const slots = useSlots();

function toggleDetails() {
    isOpen.value = !isOpen.value;
}

const extraProps = computed(() => slots.title ? {/* no props */} : {
    role: "button",
    onClick: toggleDetails
})
</script>

<template>
    <div class="details">
        <div v-bind="extraProps" class="title">
            <slot name="title" :isOpen :toggleDetails>Spoiler</slot>
        </div>
        <div v-show="isOpen" class="content"><slot>Default filler</slot></div>
    </div>
</template>

<style scoped>
.details {
    border: 1px solid black;
}

.title {
    background-color: lightgray;
    cursor: pointer;
    padding: 4px;
}

.content {
    padding: 8px;
}
</style>