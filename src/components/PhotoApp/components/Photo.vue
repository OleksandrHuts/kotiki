<template>
    <div class="ba-filtered-img-wrap">
        <img v-if="srcVal" class="ba-filtered-img"
            :src="srcVal"
            alt="CSSgram">
    </div>
</template>

<script>
export default {
    name: 'Photo',
    props: {
        srcVal: {
            type: String,
            required: true
        }
    }
}
</script>