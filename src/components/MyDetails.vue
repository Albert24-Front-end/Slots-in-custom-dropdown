<script setup lang="ts">
import { ref } from 'vue';

const isOpen = ref(false);

</script>

<template>
    <div class="details">
        <div @click="isOpen = !isOpen" class="title">
            <slot name="title" :isOpen>Spoiler</slot>
        </div>
        <div v-show="isOpen" class="content"><slot></slot></div>
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