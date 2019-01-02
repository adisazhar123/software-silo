<template>
  <v-form>
    <br><br><br>
    <v-container fluid>
      <v-layout row wrap>
        <v-flex xs12 sm6>
          <v-text-field
            v-model="email"
            :rules="emailRules"
            label="E-mail"
            required
          ></v-text-field>
          <v-text-field
            v-model="password"
            :append-icon="show1 ? 'visibility_off' : 'visibility'"
            :rules="[rules.required]"
            :type="show1 ? 'text' : 'password'"
            name="input-10-1"
            label="Normal with hint text"
            hint="At least 8 characters"
            counter
            @click:append="show1 = !show1"
          ></v-text-field>          
          <v-btn color="primary" flat @click="register">Submit</v-btn>
        </v-flex>        
      </v-layout>
    </v-container>
  </v-form>

</template>


<style scoped>

</style>


<script>
export default {
  data () {
    return {
      show1: false,      
      password: '',
      rules: {
        required: value => !!value || 'Required.',        
        emailMatch: () => ('The email and password you entered don\'t match')
      },
      
      email: '',
      emailRules: [
        v => !!v || 'E-mail is required',
        v => /.+@.+/.test(v) || 'E-mail must be valid'
      ]
    }
  },

  methods: {
    async register() {
      let user;
      try {
        user = await this.$axios.post('register', {
          email: this.email,
          password: this.password
        });
      } catch (error) {
        return console.log(error);
      }
      console.log(user)
    }
  }
}
</script>
