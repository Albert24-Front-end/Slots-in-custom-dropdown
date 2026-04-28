<script setup lang="ts">
import MyDetails from './components/MyDetails.vue';
</script>

<template>
    <h1>Learning slots in Vue 3</h1>
    <MyDetails>
        <template #title="{isOpen}">
            <button>
                <template v-if="isOpen"> - </template>
                <template v-else> + </template>
            </button>
            Title
        </template>
        <template #default="{ isOpen }"><p>Details content {{ isOpen }}</p></template>
    </MyDetails>
</template>
