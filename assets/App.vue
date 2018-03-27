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
        <router-view></router-view>
      </v-container>
    </v-content>
    <v-footer :fixed="fixed" app>
      <span>© 2018 Nimble, All rights reserved.</span>
    </v-footer>
  </v-app>
  <!--<v-app>-->

  <!--<v-toolbar fixed>-->
  <!--<v-toolbar-side-icon @click.stop="drawer = !drawer"></v-toolbar-side-icon>-->
  <!--</v-toolbar>-->
  <!--<v-toolbar fixed app :clipped-left="clipped">-->
  <!--<v-toolbar-side-icon @click.stop="drawer = !drawer"></v-toolbar-side-icon>-->
  <!--<v-btn-->
  <!--icon-->
  <!--@click.native.stop="miniVariant = !miniVariant"-->
  <!--&gt;-->
  <!--<v-icon v-html="miniVariant ? 'chevron_right' : 'chevron_left'"></v-icon>-->
  <!--</v-btn>-->
  <!--<v-btn-->
  <!--icon-->
  <!--@click.native.stop="clipped = !clipped"-->
  <!--&gt;-->
  <!--<v-icon>web</v-icon>-->
  <!--</v-btn>-->
  <!--<v-btn-->
  <!--icon-->
  <!--@click.native.stop="fixed = !fixed"-->
  <!--&gt;-->
  <!--<v-icon>remove</v-icon>-->
  <!--</v-btn>-->
  <!--<v-toolbar-title v-text="title"></v-toolbar-title>-->
  <!--<v-spacer></v-spacer>-->
  <!--<v-btn-->
  <!--icon-->
  <!--@click.native.stop="rightDrawer = !rightDrawer"-->
  <!--&gt;-->
  <!--<v-icon>menu</v-icon>-->
  <!--</v-btn>-->
  <!--</v-toolbar>-->
  <!--<v-content>-->
  <!--<v-container fluid>-->
  <!--<v-slide-y-transition mode="out-in">-->
  <!--<router-view></router-view>-->
  <!--</v-slide-y-transition>-->
  <!--</v-container>-->
  <!--</v-content>-->
  <!--&lt;!&ndash;<v-navigation-drawer&ndash;&gt;-->
  <!--&lt;!&ndash;temporary&ndash;&gt;-->
  <!--&lt;!&ndash;:right="right"&ndash;&gt;-->
  <!--&lt;!&ndash;v-model="rightDrawer"&ndash;&gt;-->
  <!--&lt;!&ndash;fixed&ndash;&gt;-->
  <!--&lt;!&ndash;&gt;&ndash;&gt;-->
  <!--&lt;!&ndash;<v-list>&ndash;&gt;-->
  <!--&lt;!&ndash;<v-list-tile @click.native="right = !right">&ndash;&gt;-->
  <!--&lt;!&ndash;<v-list-tile-action>&ndash;&gt;-->
  <!--&lt;!&ndash;<v-icon light>compare_arrows</v-icon>&ndash;&gt;-->
  <!--&lt;!&ndash;</v-list-tile-action>&ndash;&gt;-->
  <!--&lt;!&ndash;<v-list-tile-title>Switch drawer (click me)</v-list-tile-title>&ndash;&gt;-->
  <!--&lt;!&ndash;</v-list-tile>&ndash;&gt;-->
  <!--&lt;!&ndash;</v-list>&ndash;&gt;-->
  <!--&lt;!&ndash;</v-navigation-drawer>&ndash;&gt;-->
  <!--<v-footer :fixed="fixed" app>-->
  <!--<span>&copy; 2017</span>-->
  <!--</v-footer>-->
  <!--</v-app>-->
</template>

<script>
  import Meta from 'mixins/meta'

  export default {
    mixins: [Meta],

    data() {
      return {
        clipped: false,
        drawer: true,
        fixed: false,
        items: [
          {title: 'Get Started', to: '/'},
          {title: 'Logo Animation', to: '/inspire'},

        ],
        miniVariant: false,
        right: true,
        rightDrawer: false,
        title: 'Vuetify.js'
      }
    }
  }
</script>
