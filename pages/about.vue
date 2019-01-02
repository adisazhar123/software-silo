<template>
  <div id="content">
    <div class="about">
      <v-container>
        <p>todo</p>
        <p>
          <!-- {{ loggedInUser }} -->
        </p>
      </v-container>
    </div>

  </div>
</template>

<script>
import { mapGetters } from 'vuex'

export default {
  // middleware: 'auth',
  computed: {
    ...mapGetters(['loggedInUser'])
  }
}
</script>

<style scoped>
  #content {
    background-color: #b8e994;
    height: 100%;
  }

  .about {
    padding-top: 100px;
    height: 900px;
  }

</style>
