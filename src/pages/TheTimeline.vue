<template>
    <div>
        <ul>
            <TimeLineItem v-for="timelineItem in timeLineItems" :key="timelineItem.hour"
                :timeline-item="timelineItem" />
        </ul>
    </div>
</template>

<script setup>
import TimeLineItem from "@/components/TimeLineItem.vue";

defineProps(['timeLineItems'])
</script>

<style lang="scss" scoped></style>