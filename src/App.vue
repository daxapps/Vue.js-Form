<template>
  <div id="app">
    <div class='ui three column centered grid'>
      <div class='column'>
        <create-risk v-on:create-risk="createRisk"></create-risk>
        <create-feature v-on:create-feature="createFeature"></create-feature>
        <!-- <brite-core v-bind:risks="risks"></brite-core> -->
        <!-- <brite-core v-bind:features="features"></brite-core> -->
      </div>
    </div>
  </div>
</template>
<script type="text/javascript">
import BriteCore from './components/BriteCore';
import CreateRisk from './components/CreateRisk';

export default {
  name: 'app',
  components: {
    BriteCore,
    CreateRisk,
  },
  data() {
    return {
      risk: [],
      features: [],
    };
  },
};
</script>
<style>


</style>
