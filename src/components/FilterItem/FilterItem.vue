<template>
    <div class="ba-filter">
        <div class="ba-filter__top">
            <label for="blur">
                {{ filterItem.label }}:
            </label>
            <span class="ba-filter__value">
                {{ rangeValue }}
                {{ filterItem.dimension }}
            </span>
        </div>
        <input
            @change="onInputChanged"
            v-model="rangeValue"
            class="range"
            type="range"
            min="0"
            :id="filterItem.id"
            :name="filterItem.id"
            :max="filterItem.max">
    </div>
</template>

<script>
export default {
    name: 'FilterItem',
    props: {
        filterItem: {
            type: Object,
            required: true
        }
    },
    data() {
        return {
            rangeValue: this.filterItem.default
        }
    },
    mounted() {
        this.onInputChanged();
    },
    methods: {
        onInputChanged() {
            this.$emit('updateState', this.filterItem.id, this.rangeValue);
        }
    }
}
</script>