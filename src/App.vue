<template>
  <TheHeader @go-to-timeline="goTo(PAGE_TIMELINE)" @go-to-progress="goTo(PAGE_PROGRESS)" />
  <main class="main-container">
    <TheTimeline v-show="currentPage === PAGE_TIMELINE" />
    <TheActivities v-show="currentPage === PAGE_ACTIVITIES" />
    <TheProgress v-show="currentPage === PAGE_PROGRESS" />
  </main>
  <TheNav :current-page="currentPage" @navigate="goTo($event)" />
</template>

<script setup>
import TheHeader from "@/components/TheHeader.vue";
import TheNav from "@/components/TheNav.vue";
import TheTimeline from "@/pages/TheTimeline.vue";
import TheActivities from "@/pages/TheActivities.vue";
import TheProgress from "@/pages/TheProgress.vue";
import { PAGE_TIMELINE, PAGE_ACTIVITIES, PAGE_PROGRESS } from "@/constants";

import { normalizePageHash } from "@/functions";

import { ref } from "vue";

const currentPage = ref(normalizePageHash());


function goTo(page) {
  currentPage.value = page;
}

</script>

<style lang="scss" scoped>
* {
  all: initial;
}

.main-container {
  display: flex;
  flex-grow: 1;
  flex-direction: column;
}
</style>