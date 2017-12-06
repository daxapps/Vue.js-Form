<template>
  <div class='ui centered card'>
    <div class="content">
        <div class='field'>
          <label>Custom Risk Policy</label>
          <input type='text' v-model="risk.name" placeholder="Full Coverage" >
        </div>
      </div>
    </div>
  </div>
</template>

<script type="text/javascript">
export default {
  props: ['risk'],
  data () {
    return {
      isEditing: false
    }
  },
  methods: {
    completeRisk (risk) {
      this.$emit('complete-risk', risk)
    },
    showForm () {
      this.isEditing = true
    },
    hideForm () {
      this.isEditing = false
    }
  }
}
</script>