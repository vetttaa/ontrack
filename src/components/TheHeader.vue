<template>
    <header class="header-container">
        <TheLogo />
        <TheHeaderProgress />
    </header>
</template>

<script setup>
import TheLogo from "@/components/TheLogo.vue";
import TheHeaderProgress from "@/components/TheHeaderProgress.vue";

</script>

<style lang="scss" scoped>
.header-container {
    position: sticky;
    top: 0;
    z-index: 20;
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-bottom: 1px solid #ccc;
    background: #ffffff;
    padding: 3px;
}
</style>