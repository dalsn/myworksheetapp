<template>
  <section>
    <p>{{ question }}</p>
    <ul>
      <li v-for="(option, key) in options" :key="key">{{ option.text }}</li>
    </ul>
  </section>
</template>

<script>
export default {
  name: 'PreviewPane',
  props: {
    options: {
      type: Array,
      required: true
    },
    question: {
      type: String,
      required: true
    }
  }
}
</script>

<style scoped>

</style>
