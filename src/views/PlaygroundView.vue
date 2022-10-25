<template>
  <div>
    <CreditCardForm />
    <slider animation="fade">
      <slider-item v-for="(i, index) in list" :key="index" :style="i">
        <p style="line-height: 280px; font-size: 5rem; text-align: center;">Page{{ index + 1 }}</p>
      </slider-item>
    </slider>
  </div>
</template>

<script>
import CreditCardForm from '../components/CreditCardForm/CreditCardForm.vue';
import { Slider, SliderItem } from 'vue-easy-slider';

export default {
  components: {
    CreditCardForm,
    Slider,
    SliderItem
  },
  data() {
    return {
      list: [
        { backgroundColor: '#3f51b5', width: '100%', height: '100%' },
        { backgroundColor: '#eee', width: '100%', height: '100%' },
        { backgroundColor: '#f44336', width: '100%', height: '100%' },
      ],
    }
  }
}
</script>
