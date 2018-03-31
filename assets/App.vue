<template>
  <v-app>
    <v-navigation-drawer
      :mini-variant="miniVariant"
      :clipped="clipped"
      v-model="drawer"
      fixed
      app
    >
      <v-list>
        <v-list-tile router :to="item.to" :key="i" v-for="(item, i) in items" exact>
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
      fixed
      app
      :clipped-left="clipped">

      <v-toolbar-side-icon @click.stop="drawer = !drawer">
      </v-toolbar-side-icon>


      <router-link to="/" class="">
        <v-toolbar-title>
          <div class="nav-logo">
            <router-link to="/" v-on:click.native="openNav">
              <img src="/static/svg/nimblelogo.svg" height="40" alt="Nimble"/>
            </router-link>
          </div>
        </v-toolbar-title>
      </router-link>

      <v-spacer></v-spacer>

      <v-toolbar-items class="hidden-sm-and-down">
        <v-btn flat>Home</v-btn>
        <v-btn flat>AboutUs</v-btn>
        <v-btn flat>Documentation</v-btn>
      </v-toolbar-items>

    </v-toolbar>

    <v-content>
      <v-container fluid class="no-padding">
        <router-view>

        </router-view>
      </v-container>
    </v-content>
    <v-footer :fixed="fixed" app>
      <span>© 2018 Nimble, All rights reserved.</span>
    </v-footer>
  </v-app>

</template>

<script>
  import Meta from 'mixins/meta'

  export default {
    mixins: [Meta],

    data() {
      return {
        clipped: false,
        drawer: false,
        fixed: false,
        items: [
          {title: 'Get Started', to: '/home'},
          {title: 'Logo Animation', to: '/inspire'},
          {title: 'Icon Animation', to: '/get started'}
        ],
        miniVariant: false,
        right: true,
        rightDrawer: false,
        title: 'Vuetify.js'
      }
    }
  }
</script>
