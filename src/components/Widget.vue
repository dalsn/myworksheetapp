<template>
  <section>
    <QuestionEditor @updateQuestion="updateQuestion" />
    <Options @addOption="updateOptions" />
  </section>
</template>

<script>
import QuestionEditor from './QuestionEditor.vue'
import Options from './Options.vue'

export default {
  name: 'Widget',
  components: {
    QuestionEditor,
    Options
  },
  data () {
    return {
      options: [],
      question: ''
    }
  },
  methods: {
    updateQuestion (question) {
      this.$emit('updateWorksheet', {question: question})
    },
    updateOptions (option) {
      this.$emit('updateWorksheet', {option: {...option}})
    }
  }
}
</script>

<style scoped>

</style>
