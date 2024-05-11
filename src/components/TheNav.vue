<template>
    <nav class="nav-container">
        <ul>
            <li v-for="icon, page in navItems" :key="page">
                <a :href="`#${page}`" class="nav-link">
                    <component :is="icon" class="nav-icon" />{{ page }}
                </a>
            </li>
        </ul>
    </nav>
</template>

<script setup>
import { ClockIcon, ListBulletIcon, ChartBarIcon } from "@heroicons/vue/24/outline";

const navItems = {
    timeline: ClockIcon,
    activities: ListBulletIcon,
    progress: ChartBarIcon
};
</script>

<style lang="scss" scoped>
* {
    all: initial;
}

.nav-container {
    position: sticky;
    bottom: 0;
    z-index: 10;
    background-color: #ffffff;
    border-top: 1px solid #ccc;
    padding: 4px;

    ul {
        display: flex;
        align-items: center;
        justify-content: space-around;


        li {
            flex: 1;
        }
    }

    .nav-link {
        display: flex;
        flex-direction: column;
        align-items: center;
        padding: 2px;
        font-size: medium;
    }

    .nav-icon {
        height: 1.5em;
        width: 1.5em;
    }
}
</style>