<template>
  <div>
  </div>
</template>

<script>
import sweetalert from 'sweetalert';
import Risk from './Risk';
import Feature from './Feature';

export default {
  props: ['risk', 'features'],
  components: {
    Risk,
    Feature
  },
  methods: {
    completeFeature (feature) {
      const featureIndex = this.features.indexOf(feature)
      this.features[featureIndex].done = true
      sweetalert('Success!', 'Feature Added!', 'success')
    }
  }
}
</script>

<style scoped>
  p.options {
    text-align: center;
  }
</style>