<template>
  <v-form>
    <br><br><br>
    <v-container>
      <v-layout  wrap align-center 
      justify-center fill-height>
        <v-flex xs12 sm6>
          <alert v-if="alertMessage" :type="alertType" :message="alertMessage"/>
        </v-flex>        
      </v-layout>
      
      <v-layout wrap align-center 
      justify-center fill-height>     
        <v-flex xs12 sm6>
          <v-text-field
            v-model="email"
            :rules="emailRules"
            label="E-mail"
            required
            color="white"
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
            color="white"
            @click:append="show1 = !show1"
          ></v-text-field>          
          <v-btn color="white" @click="login"
          style="width: 100%">Submit</v-btn>
        </v-flex>        
      </v-layout>
    </v-container>
  </v-form>

</template>


<style scoped>

</style>


<script>
import alert from "~/components/Alert";

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
      ],
      alertMessage:'',
      alertType:'success',
      disableBtn: false
    }
  },

  components: {
    alert
  },
  
  middleware: 'auth',
  
  methods: {
    async login() {
      let res;
      try {
        res = await this.$auth.login({
          data: {
            email: this.email,
            password: this.password
          }
        });         
      } catch (error) {        
        this.alertMessage = error.response.data.message;                
        this.alertType = 'error';
        return console.log(error);
      }
      let self = this;
      this.alertType = 'success';
      this.alertMessage = 'Login successful.'
      this.disableBtn = true;

      setTimeout(() => {        
        self.$router.push('/');
      }, 2000);      
      
    }
  }
}
</script>
