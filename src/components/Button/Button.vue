<template>
    <button class="btn">
        <slot name="label">
            Sent
        </slot>
        |
        <slot name="image">
            ©
        </slot>
    </button>
</template>

<script>
    export default {
        name: 'Button'
    }
</script>

<style lang="scss" scoped src="./style.scss"></style>