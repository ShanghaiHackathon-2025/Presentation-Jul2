<template>
    <div class="h-stack">
        <slot />
    </div>
</template>

<script setup>
</script>

<style scoped>
.h-stack {
    display: flex;
    flex-direction: row;
    align-items: flex-start;
    gap: 1rem; /* Adjust spacing as needed */
}
</style>