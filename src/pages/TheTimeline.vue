<template>
    <div>
        <ul>
            <li v-for="{ hour } in timeLineItems" :key="hour" class="timeline-item">
                <a href="#" class="timeline-link">{{ hour }}:00</a>
            </li>
        </ul>
    </div>
</template>

<script setup>
import { generationTimelineItems } from "@/functions";

const timeLineItems = generationTimelineItems()

</script>

<style lang="scss" scoped>
.timeline-item {
    position: relative;
    display: flex;
    flex-direction: column;
    gap: 2px;
    border-top: 1px solid #ccc;
    padding: 20px 4px;
}

.timeline-link {
    background-color: rgb(228, 225, 225);
    padding: 2px;
    font-family: monospace;
    font-size: 18px;
    color: #4b4a4a;

    position: absolute;
    top: 10px;
    left: 50%;
    translate: -50%;
}
</style>