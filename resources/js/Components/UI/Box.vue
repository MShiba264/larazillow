<script setup>
</script>
<template>
    <div class="border border-gray-200 dark:border-gray-800 rounded-md shadow-sm dark:text-gray-300">
        <div class="text-gray-500 font-medium">
            <slot name="header" />
        </div>
        <slot />
    </div>
</template>
<style scoped>
</style>
