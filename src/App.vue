<template>
  <v-app>
    <v-navigation-drawer
      persistent
      :mini-variant="false"
      clipped
      v-model="drawer"
      enable-resize-watcher
      fixed
      app
    >
      <v-list>
        <v-list-tile
          value="true"
          v-for="(item, i) in items"
          :key="i"
        >
          <v-list-tile-action>
            <v-icon v-html="item.icon"></v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title v-text="item.title"></v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar
      color="primary white--text"
      app
      clipped-left
    >
      <v-toolbar-side-icon color="primary" @click.stop="drawer = !drawer"></v-toolbar-side-icon>
      <v-toolbar-title v-text="title"></v-toolbar-title>
      <v-spacer></v-spacer>
    </v-toolbar>
    <v-content>
      <router-view/>
    </v-content>
    <v-footer :fixed="fixed" app>
      <span>&copy; 2018</span>
      <v-spacer></v-spacer>
      <a href="https://github.com/lyonsbp/registertovote.how">Github repo</a>
    </v-footer>
  </v-app>
</template>

<script>

export default {
  name: 'App',
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [{
        icon: 'bubble_chart',
        title: 'Inspire'
      }],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'registertovote.how'
    }
  },
  methods: {

  }
}
</script>

<style lang="scss" scoped>
 #app {
  background: linear-gradient(90deg, #3F2B96 0%, #A8C0FF 100%);
 }

 a {
  color: #2972C2;
 }
</style>
