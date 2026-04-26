<script setup lang="ts">
const {title = 'Spoiler'} = defineProps<{
    title?: string,
}>()
</script>

<template>
    <div class="details">
        <div class="title">{{ title }}</div>
        <div class="content"><slot></slot></div>
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