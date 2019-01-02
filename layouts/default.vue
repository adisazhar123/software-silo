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

        <v-list-tile v-if="loggedInUser" @click="logout">
            <v-list-tile-action>
            <v-icon>
              apps
            </v-icon>
          </v-list-tile-action>
            <v-list-tile-content>
              <v-list-tile-title>Logout</v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>

          <v-list-tile v-else to="/login">
          <v-list-tile-action>
          <v-icon>
            apps
          </v-icon>
        </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title>Login</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>

      </v-list>
    </v-navigation-drawer>
    <v-toolbar
      fixed
      :dark="isAboveY()"
      height="70"
      :color="setTransparent()"
      flat      
    >
    <nuxt-link to="/" style="text-decoration: none;">
      <v-toolbar-title v-bind:class="titleColorClass" v-text="title" style="font-weight: bolder; font-size: 28px">      
      </v-toolbar-title>
    </nuxt-link>



      <v-spacer/>

      <v-toolbar-items class="hidden-md-and-down">
        <v-btn to="/" flat>Home</v-btn>
        <v-btn to="/about" flat>About</v-btn>
        <v-btn to="/services" flat>Services</v-btn>
        <v-btn v-if="!loggedInUser" to="/login" flat>Login</v-btn>        
        <v-btn v-else flat @click="logout">Logout</v-btn>      
      </v-toolbar-items>

      <div class="toolbar-side hidden-md-and-up">
        <v-toolbar-side-icon @click="drawer = !drawer">
          <v-icon color="white" style="font-size: 44px">menu</v-icon>
        </v-toolbar-side-icon>
      </div>
    </v-toolbar>

    <v-content>
      <nuxt v-scroll="onScroll" />
      <s-footer/>
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
  import { mapGetters } from 'vuex';
  import footer from '~/components/Footer';

  export default {
    data() {
      return {
        drawer: false,
        fixed: false,
        items: [
          { icon: 'apps', title: 'Home', to: '/' },
          { icon: 'bubble_chart', title: 'About', to: '/about' },
          { icon: 'bubble_chart', title: 'Services', to: '/services' }
        ],
        title: 'Software Silo',
        scrollThreshold: 20,
        currentYPos: 0,
        titleColorClass: 'title-black'
      }
    },
    computed: {
    ...mapGetters(['loggedInUser', 'loggedInUser']),
    },
    components: {
      "s-footer": footer
    },
    mounted () {
      this.$nextTick(() => {
        this.$nuxt.$loading.start()

        setTimeout(() => this.$nuxt.$loading.finish(), 200)
      })
    },

    methods: {
      onScroll (e) {
        this.currentYPos = window.pageYOffset;
      },

      changeTitleColour(value) {
        if (value) {
         this.titleColorClass = 'title-white'; 
        } else {
          this.titleColorClass = 'title-black'; 
        }        
      },

      isAboveY() {
        if (this.currentYPos > 20) {
          this.changeTitleColour(true);
          return true;
        }
        this.changeTitleColour(false);
        return false;
      },
      setTransparent() {
        if (this.currentYPos > 20) {          
          return "";
        }
        return "transparent";
      },
            
      async logout() {
        await this.$auth.logout();
      }

    }

  }
</script>

<style media="screen">
  html {
    font-family: 'Lato', sans-serif;
  }
  .v-content {
    /* background-color: #3fc7c3; */
  }
  .v-toolbar__title{
    font-size: 24px;
  }

  .title-black {
    color: black !important;
  }

  .title-white {
    color: white !important;
  }

  /* Transitions using the page hook */
  page-enter-active, .page-leave-active {
    transition: all .30s ease-out;
  }
  .page-enter, .page-leave-active {
    opacity: 0;
    transform-origin: 50% 50%;
  }

  .v-toolbar__items .v-btn--active{
    border-bottom: solid 3px white;
    border-bottom-left-radius: 0px;
    border-bottom-right-radius: 0px;
  }

</style>
