<template lang="pug">
  v-navigation-drawer(v-model="visibility" app)
    v-list
      v-list-item
        router-link( to="/") Home
      v-list-item
        router-link(to="/about") About
</template>

<script>
export default {
  props: {
    value: {
      type: Boolean,
      default: false
    }
  },
  data() {
    return {
      visibility: this.value
    }
  },
  watch: {
    value: {
      immediate: true,
      handler() {
        if(this.visibility !== this.value) this.visibility = this.value
      }
    },
    visibility() {
      this.$emit('input', this.visibility)
    }
  }
}
</script>