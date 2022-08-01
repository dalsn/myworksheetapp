<template>
  <div class="mt-4">
    <div class="form-group mb-3">
      <input type="text" class="form-control" v-model="option.text">
    </div>
    <div class="form-check">
      <input class="form-check-input" type="radio" v-model="option.valid" id="valid" value="yes">
      <label class="form-check-label" for="valid">
        Is this the answer?
      </label>
    </div>
    <button class="btn btn-secondary" @click="addOption">Add</button>
    <button class="btn btn-success">Save!</button>
  </div>
</template>

<script>
export default {
  name: 'Options',
  data () {
    return {
      option: {
        text: '',
        valid: 'no'
      }
    }
  },
  methods: {
    addOption () {
      if (!this.option.text) {
        alert('Please provide a text for the option')
        return
      }

      this.$emit('addOption', {...this.option})
      this.option.text = ''
      this.option.valid = 'no'
    }
  }
}
</script>

<style scoped>
.options .option {
  margin-right: 1rem;
}
</style>
