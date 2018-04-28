<template>
    <div>
        <input v-model="input" />
        <button @click="submit">Submit</button>
    </div>
</template>

<script>
export default {
  data: function () {
    return {
      input: ''
    }
  },
  methods: {
    submit () {
      this.$emit('updated', this.input)
      this.input = ''
    }
  }
}
</script>

<style lang="scss" scoped>

</style>
