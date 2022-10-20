<template>
    <div class="ba-filters">
        <FilterItem
            v-for="(filter, index) in filtersArr"
            :key="index"
            :filter-item="filter"
            @updateState='updateState'/>

        <button class="ba-clear" data-clear>Clear all</button>
    </div>
</template>

<script>
import FilterItem from '@/components/FilterItem/FilterItem.vue';

export default {
    name: 'Filters',
    components: {
        FilterItem
    },
    data() {
        return {
            filterState: {
                blur: 10,
                contrast: 100,
                hue: 0,
                sepia: 0
            },
            filtersArr: [
                {
                    label: 'blur',
                    id: 'blur',
                    dimension: 'px',
                    max: 20,
                    default: 10
                },
                {
                    label: 'contrast',
                    id: 'contrast',
                    dimension: '%',
                    max: 200,
                    default: 100
                },
                {
                    label: 'hue rotate',
                    id: 'hue',
                    dimension: 'deg',
                    max: 360,
                    default: 0
                },
                {
                    label: 'sepia',
                    id: 'sepia',
                    dimension: '%',
                    max: 100,
                    default: 0
                }]
        }
    },
    methods: {
        updateState(id, value) {
            this.filterState[id] = value;

            const html = document.getElementsByTagName('html')[0];
            html.style.cssText = this.htmlStyle;
        }
    },
    computed: {
        htmlStyle() {
            return `--contrast:${this.filterState.contrast}%; --hue:${this.filterState.hue}deg; --sepia:${this.filterState.sepia}%; --saturate:${this.filterState.saturate}%; --blur:${this.filterState.blur}px;`;
        }
    }
}
</script>