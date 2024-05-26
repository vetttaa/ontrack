<template>
    <div class="timeline-select-container">
        <BaseButton>
            <XMarkIcon class="icon" />
        </BaseButton>
        <select class="timeline-select">
            <option selected disabled value="">{{ placeholder }}</option>
            <option v-for="{ value, label } in options" :key="value" value="" :selected="select === value">{{ label }}
            </option>
        </select>
    </div>
</template>

<script setup>
import BaseButton from "./BaseButton.vue";
import { XMarkIcon } from "@heroicons/vue/24/outline";


defineProps(['placeholder', 'options', 'select'])

</script>

<style lang="scss" scoped>
.timeline-select-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 4px;
}

.timeline-select {
    width: 100%;
    height: 2em;
    padding: 1px 2px;
    font-size: 16px;
    font-family: monospace;
    color: #4b4a4a;
    background-color: #f0f0f0;
    border: none;
    border-radius: 4px;
    outline: none;
}

.icon {
    height: 1.5em;
}
</style>