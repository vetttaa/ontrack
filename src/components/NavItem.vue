<template>
    <li>
        <a v-bind="$attrs" class="nav-link">
            <slot></slot>
        </a>
    </li>
</template>

<script>
export default {
    inheritAttrs: false
}
</script>

<style lang="scss" scoped>
.nav-link {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 2px;
    font-size: medium;
}
</style>
