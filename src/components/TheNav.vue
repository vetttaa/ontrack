<template>
    <nav class="nav-container">
        <ul>
            <NavItem v-for="(icon, page) in navItems" :key="page" :href="`#${page}`"
                :class="{ 'active': page === currentPage }" @click="currentPage = page">
                <component :is="icon" class="nav-icon" />{{ page }}
            </NavItem>
        </ul>
    </nav>
</template>

<script setup>
import { ClockIcon, ListBulletIcon, ChartBarIcon } from "@heroicons/vue/24/outline";
import { PAGE_TIMELINE, PAGE_ACTIVITIES, PAGE_PROGRESS } from "@/constants";
import NavItem from "@/components/NavItem.vue";
import { ref } from "vue";

const navItems = {
    [PAGE_TIMELINE]: ClockIcon,
    [PAGE_ACTIVITIES]: ListBulletIcon,
    [PAGE_PROGRESS]: ChartBarIcon
};

const currentPage = ref(normalizePageHash());

function normalizePageHash() {
    const hash = window.location.hash.slice(1);
    if (Object.keys(navItems).includes(hash)) {
        return hash;
    }
    window.location.hash = PAGE_TIMELINE;
    return PAGE_TIMELINE;
}

</script>

<style lang="scss">
.nav-container {
    position: sticky;
    bottom: 0;
    z-index: 10;
    background-color: #ffffff;
    border-top: 1px solid #ccc;

    ul {
        display: flex;
        align-items: center;
        justify-content: space-between;
        margin: 0;
        padding: 0;


        li {
            flex: 1;
        }
    }

    .nav-icon {
        height: 1.5em;
        width: 1.5em;
    }
}

.active {
    background-color: rgb(206, 206, 206);
    pointer-events: none;
    height: 4em
}
</style>