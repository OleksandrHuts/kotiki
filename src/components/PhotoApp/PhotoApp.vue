<template>
    <div class="ba-container">
        <Header />
        <Controls />
        <div class="ba-row">
            <div class="ba-col-8">
                <Photo srcVal='https://t3.ftcdn.net/jpg/02/95/94/94/360_F_295949484_8BrlWkTrPXTYzgMn3UebDl1O13PcVNMU.jpg'/>
            </div>
            <div class="ba-col-4">
                <Filters />
            </div>
        </div>
    </div>
</template>

<script>
import Photo from './components/Photo.vue';
import Header from './components/Header.vue';
import Filters from './components/Filters.vue';
import Controls from './components/Controls.vue';

export default {
    name: 'PhotoApp',
    components: {
        Photo,
        Header,
        Filters,
        Controls
    }
}
</script>

<style lang="scss" src="./style.scss">

</style>