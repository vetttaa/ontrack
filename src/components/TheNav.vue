<template>
    <nav class="nav-container">
        <ul>
            <NavItem v-for="(icon, page) in NAV_ITEMS" :key="page" :href="`#${page}`"
                :class="{ 'active': page === currentPage }" @click="emit('navigate', page)">
                <component :is="icon" class="nav-icon" />{{ page }}
            </NavItem>
        </ul>
    </nav>
</template>

<script setup>
import { NAV_ITEMS } from "@/constants";
import NavItem from "@/components/NavItem.vue";

defineProps(['currentPage']);

const emit = defineEmits(['navigate'])

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