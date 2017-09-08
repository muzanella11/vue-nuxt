<template>
  <v-app
    height="415px"
    id="e3"
    standalone
    toolbar
  >
    <!-- Begin Navigation Drawer -->
    <v-navigation-drawer
      class="bongo l-aside l-aside--grey pb-0"
      persistent
      absolute
      height="100%"
      clipped
      enable-resize-watcher
      v-model="drawer"
      style="position: fixed;"
    >
      <v-list dense>
        <v-list-tile v-for="item in items" :key="item.text" :to="item.to" exact @click="">
          <v-list-tile-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title>
              {{ item.title }}
            </v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
        <v-subheader class="mt-3 grey--text text--darken-1">SUBSCRIPTIONS</v-subheader>
        <v-list>
          <v-list-tile v-for="item in items2" :key="item.text" avatar @click="">
            <v-list-tile-avatar>
              <img :src="`https://randomuser.me/api/portraits/men/${item.picture}.jpg`" alt="">
            </v-list-tile-avatar>
            <v-list-tile-title v-text="item.title"></v-list-tile-title>
          </v-list-tile>
        </v-list>
        <v-list-tile class="mt-3" @click="">
          <v-list-tile-action>
            <v-icon class="grey--text text--darken-1">add_circle_outline</v-icon>
          </v-list-tile-action>
          <v-list-tile-title class="grey--text text--darken-1">Browse Channels</v-list-tile-title>
        </v-list-tile>
        <v-list-tile @click="">
          <v-list-tile-action>
            <v-icon class="grey--text text--darken-1">settings</v-icon>
          </v-list-tile-action>
          <v-list-tile-title class="grey--text text--darken-1">Manage Subscriptions</v-list-tile-title>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <!-- End Navigation Drawer -->

    <!-- Begin Toolbar -->
    <v-toolbar class="bongo l-header l-header--green" :fixed="toolbarFixed">
      <v-toolbar-title>
        <v-toolbar-side-icon @click.stop="drawer = !drawer"></v-toolbar-side-icon>
        Nama Apps
        <v-icon class="ml-3">fa-youtube</v-icon>
      </v-toolbar-title>
    </v-toolbar>
    <!-- End Toolbar -->

    <!-- Begin Main Content -->
    <main id="mainContent" class="bongo l-main-content">
      <v-container id="mainContentContainer">
        <nuxt />
        <v-layout>
          <v-flex xs12>
            <v-card height="3000px"></v-card>
          </v-flex>
        </v-layout>
      </v-container>
    </main>
    <!-- End Main Content -->
  </v-app>
</template>

<script>
export default {
  name: 'bongo-layouts',
  data () {
    return {
      toolbarFixed: true,
      drawer: true,
      fixed: true,
      items: [
        { to: '/', title: 'Welcome', icon: 'apps' },
        { to: '/inspireyou', title: 'Inspire You', icon: 'bubble_chart' },
        { to: '/inspire', title: 'Inspire', icon: 'bubble_chart' },
        { to: '/inspire', title: 'Inspire', icon: 'bubble_chart' },
        { to: '/inspire', title: 'Inspire', icon: 'bubble_chart' },
        { to: '/inspire', title: 'Inspire', icon: 'bubble_chart' },
        { to: '/inspire', title: 'Inspire', icon: 'bubble_chart' },
        { to: '/inspire', title: 'Inspire', icon: 'bubble_chart' },
        { to: '/inspire', title: 'Inspire', icon: 'bubble_chart' },
        { to: '/inspire', title: 'Inspire', icon: 'bubble_chart' },
        { to: '/inspire', title: 'Inspire', icon: 'bubble_chart' }
      ],
      items2: [
        { to: '/', title: 'Welcome', picture: '8' },
        { to: '/inspire', title: 'Inspire', picture: '11' }
      ]
    }
  },

  created () {

  }
}
</script>
