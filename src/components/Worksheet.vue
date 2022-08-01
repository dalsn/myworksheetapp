<template>
  <section class="row">
    <div class="col-lg-6">
      <Widget @updateWorksheet="updateWorksheet" />
    </div>
    <div class="col-lg-6">
      <PreviewPane :question="question" :options="options" />
    </div>
  </section>
</template>

<script>
import Widget from './Widget.vue'
import PreviewPane from './PreviewPane.vue'

export default {
  name: 'Worksheet',
  components: {
    Widget,
    PreviewPane
  },
  data () {
    return {
      question: '',
      options: []
    }
  },
  methods: {
    updateWorksheet (worksheet) {
      this.question = worksheet.question ? worksheet.question : this.question
      if (worksheet.option) this.options.push({...worksheet.option})
    }
  }
}
</script>

<style scoped>

</style>
