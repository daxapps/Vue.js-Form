<template>
  <div class='ui basic content center aligned segment'>
    <div class='ui centered card' v-show="isCreating">
      <div class='content'>
        <div class='ui form'>
          <div class="field" >
            <button class='ui basic blue button'  v-on:click="addRisk()" >
              Add Risks
              <i class='plus icon blue'></i>
            </button>
          </div>
          <risk  v-for="risk in policy.risks" key="risk.id" :risk.sync="risk"></risk>
        </div>
        <div class='ui form'>
          <div class="field" >
            <button class='ui basic blue button'  v-on:click="addFeature()" >
              Add Features
              <i class='plus icon blue'></i>
            </button>
          </div>
          <feature  v-for="feature in policy.features" key="feature.id" :feature.sync="feature"></feature>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import sweetalert from 'sweetalert';
import Risk from './Risk';
import Feature from './Feature';

export default {
  components: {
    Risk,
    Feature
  },
  data() {
    return {
      policy: {
        risks: [],
        features: []
      },
      isCreating: true,
    };
  },
  methods: {
    completeRisk(risk) {
      this.$emit('complete-risk', risk);
    },
    completeRisk(feature) {
      this.$emit('complete-feature', feature);
    },
    openForm() {
      this.isCreating = true;
    },
    closeForm() {
      this.isCreating = false;
    },
    addRisk() {
      this.policy.risks.push({ name: '', value: '' });
    },
    addFeature() {
      this.policy.features.push({ name: '', value: '' });
    },
  },
};
</script>