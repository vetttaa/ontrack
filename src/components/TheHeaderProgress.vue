<template>
    <a href="#">
        <div class="header-status-container">
            Day complete
            <CheckCircleIcon class="icon-complete" />
        </div>

        <div class="header-status-container">
            <div>Progress: <span>50%</span></div>
            <div class="circle-progress"></div>
        </div>
    </a>
</template>

<script setup>
import { CheckCircleIcon } from "@heroicons/vue/24/solid";
</script>

<style lang="scss" scoped>
.header-status-container {
    display: flex;
    align-items: center;
    gap: 1px;
    font-size: 1em;

    .icon-complete {
        height: 1.5em;
        color: green;
    }

    .circle-progress {
        width: 1.2em;
        height: 1.2em;
        background-color: orange;
        border-radius: 50%;
    }
}
</style>