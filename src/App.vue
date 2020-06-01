<template lang="pug">
v-app
  main-navigation(v-model="drawerVisibility")
  v-app-bar.text-center(app absolute dark)
    v-app-bar-nav-icon(@click="moveDrawer")
    v-toolbar-title Spotify Integration Project

  v-content
    router-view
</template>

<script>
import MainNavigation from '@/components/sidebars/MainNavigation.vue'
export default {
  components: {
    MainNavigation
  },
  data() {
    return {
      drawerVisibility: false
    }
  },
  methods: {
    moveDrawer() {
      this.drawerVisibility = !this.drawerVisibility
    }
  }
}
</script>