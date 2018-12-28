<template>
  <v-app>
    <v-navigation-drawer
      v-model="drawer"
      fixed
      app
      disable-resize-watcher
      temporary
    >
      <v-list>
        <v-list-tile
          v-for="(item, i) in items"
          :to="item.to"
          :key="i"
          router
          exact
        >
          <v-list-tile-action>
            <v-icon v-html="item.icon" />
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title v-text="item.title" />
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar
      fixed
      :dark="isAboveY()"
      height="64"
      :color="setTransparent()"
      flat
    >

    <v-toolbar-title v-text="title" style="font-weight: bolder; font-size: 28px">
      <img src="https://static.arkavidia.id/5/images/logo.svg" alt="">
    </v-toolbar-title>



      <v-spacer/>

      <v-toolbar-items class="hidden-md-and-down">
        <v-btn to="/" flat>Home</v-btn>
        <v-btn to="/about" flat>About</v-btn>
        <v-btn to="/services" flat>Services</v-btn>
      </v-toolbar-items>

      <div class="toolbar-side hidden-md-and-up">
        <v-toolbar-side-icon @click="drawer = !drawer">
          <v-icon color="white" style="font-size: 44px">menu</v-icon>
        </v-toolbar-side-icon>
      </div>
    </v-toolbar>

    <v-content>
      <nuxt v-scroll="onScroll" />
    </v-content>
    <v-navigation-drawer
      temporary
      fixed
      app
    >
      <v-list>
        <v-list-tile @click.native="right = !right">
          <v-list-tile-action>
            <v-icon light>compare_arrows</v-icon>
          </v-list-tile-action>
          <v-list-tile-title>Switch drawer (click me)</v-list-tile-title>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>

  </v-app>
</template>

<script>
  export default {
    data() {
      return {
        drawer: false,
        fixed: false,
        items: [
          { icon: 'apps', title: 'Home', to: '/' },
          { icon: 'bubble_chart', title: 'About', to: '/inspire' },
          { icon: 'bubble_chart', title: 'Services', to: '/inspire' }
        ],
        title: 'Software Silo',
        scrollThreshold: 20,
        currentYPos: 0,
      }
    },
    mounted () {
      this.$nextTick(() => {
        this.$nuxt.$loading.start()

        setTimeout(() => this.$nuxt.$loading.finish(), 400)
      })
    },

    methods: {
      onScroll (e) {
        this.currentYPos = window.pageYOffset;
      },
      isAboveY() {
        if (this.currentYPos > 20) {
          return true;
        }
        return false;
      },
      setTransparent() {
        if (this.currentYPos > 20) {
          console.log("iy")
          return "";
        }
        return "transparent";
      }
    }

  }
</script>

<style media="screen">
  .v-toolbar__title{
    font-size: 24px;
  }

</style>
