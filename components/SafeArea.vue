<template>
    <div class="safe-area">
        <slot />
    </div>
</template>

<script setup>
// No script logic needed for basic safe area
</script>

<style scoped>
.safe-area {
    padding-top: env(safe-area-inset-top, 16px);
    padding-bottom: env(safe-area-inset-bottom, 16px);
    padding-left: env(safe-area-inset-left, 16px);
    padding-right: env(safe-area-inset-right, 16px);
    box-sizing: border-box;
    min-height: 100vh;
    background: inherit;
}
</style>