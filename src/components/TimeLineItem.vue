<template>
    <li class="timeline-item">
        <a href="#" class="timeline-link">{{ timelineItem.hour }}:00</a>
        <BaseSelect :options="options" :placeholder="Rest" :select="selectActivityId" />
    </li>
</template>

<script setup>
import BaseSelect from "@/components/BaseSelect.vue";

defineProps(['timelineItem'])
const selectActivityId = 1

const options = [
    {
        value: 1,
        label: 'Coding'
    },
    {
        value: 2,
        label: 'Reading'
    },
    {
        value: 3,
        label: 'Running'
    }
]
</script>

<style lang="scss" scoped>
.timeline-item {
    position: relative;
    display: flex;
    flex-direction: column;
    gap: 2;
    border-bottom: 1px solid #ccc;
    padding: 1.5em 4px;
    margin-bottom: 15px;
}

.timeline-link {
    background-color: #f0f0f0;
    padding: 4px;
    font-family: monospace;
    font-size: 18px;
    color: #4b4a4a;
    border-radius: 4px;

    position: absolute;
    top: 40;
    left: 50%;
    translate: -50%;
    z-index: 10;
}
</style>