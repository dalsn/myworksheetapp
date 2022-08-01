<template>
  <div class="form-group">
    <textarea class="form-control" rows="4" v-model="question" placeholder="Enter your question" @change="updateQuestion"></textarea>
  </div>
</template>

<script>
export default {
  name: 'QuestionEditor',
  data () {
    return {
      question: ''
    }
  },
  methods: {
    updateQuestion () {
      if (!this.question) {
        alert('Please provide a text for the question')
        return
      }

      this.$emit('updateQuestion', this.question)
      this.question = ''
    }
  }
}
</script>

<style scoped>

</style>
