<template>
  <div>
    <v-container class="fill-height" fluid >
      <v-row align="center" justify="center">
        <v-col cols="12" sm="8" md="8">
          <v-card class="elevation-12">
            <v-window v-model="step">
              <v-window-item :value="1" class="cin">
                <v-row>
                  <v-col cols="12" md="8" class="accent">
                    <v-card-text class="mt-12">
                      <h1
                        class="text-center display-2 white--text"
                        style="opacity:0.8"
                      >Sign in to web</h1>
                      <div class="text-center mt-4">
                        <v-btn class="mx-2" fab color="blue" outlined style="opacity:0.8">
                          <v-icon large>mdi-facebook</v-icon>
                        </v-btn>
                        <v-btn class="mx-2" fab color="white" outlined style="opacity:0.8">
                          <v-icon large>mdi-google-plus</v-icon>
                        </v-btn>
                        <v-btn class="mx-2" fab color="black" outlined>
                          <v-icon large>mdi-github</v-icon>
                        </v-btn>
                      </div>
                      <h4 class="text-center mt-4"></h4>
                      <v-form>
                        <v-text-field
                          label="Email"
                          name="Email"
                          prepend-icon="mdi-email"
                          type="text"
                          color="white"
                          v-model="Email"
                          required
                        ></v-text-field>
                        <v-text-field
                          id="password"
                          label="Password"
                          name="Password"
                          prepend-icon="mdi-lock"
                          type="password"
                          color="white"
                          v-model="password"
                          required
                        ></v-text-field>
                      </v-form>
                      <div style="text-align:center;">
                        <v-btn text>
                          <h4 class="text-center mt-3">Forgot your password</h4>
                        </v-btn>
                      </div>
                    </v-card-text>
                    <div class="text-center mt-3">
                      <v-btn rounded dark>SIGN IN</v-btn>
                    </div>
                  </v-col>
                  <v-col cols="12" md="4">
                    <v-card-text class="white--text mt-12">
                      <h1 class="text-center display-1">Hello, friends!</h1>
                      <h3 class="text-center">Enter Your details</h3>
                    </v-card-text>
                    <div class="text-center">
                      <v-btn rounded outlined dark @click="step++">SIGN UP</v-btn>
                    </div>
                  </v-col>
                </v-row>
              </v-window-item>
              <v-window-item :value="2" class="sin">
                <v-row class="fill height">
                  <v-col cols="12" md="8" class="accent">
                    <v-card-text class="mt-12">
                      <h1
                        class="text-center display-2 white--text"
                        style="opacity:0.8"
                      >Create Account</h1>

                      <div class="text-center mt-4">
                        <h4>Or register with</h4>
                        <v-btn class="mx-2" fab color="blue" outlined style="opacity:0.8">
                          <v-icon large>mdi-facebook</v-icon>
                        </v-btn>
                        <v-btn class="mx-2" fab color="white" outlined style="opacity:0.8">
                          <v-icon large>mdi-google-plus</v-icon>
                        </v-btn>
                        <v-btn class="mx-2" fab color="black" outlined>
                          <v-icon large>mdi-github</v-icon>
                        </v-btn>
                      </div>
                      <v-form>
                        <v-text-field
                          label="Firstname"
                          name="Firstname"
                          prepend-icon="mdi-account"
                          type="text"
                          color="white"
                          v-model="firstname"
                          required
                        ></v-text-field>
                        <v-text-field
                          label="Lastname"
                          name="Lastname"
                          prepend-icon="mdi-account"
                          type="text"
                          color="white"
                          v-model="lastname"
                        ></v-text-field>
                        <v-select
                          label="Gender"
                          name="Gender"
                          prepend-icon="mdi-gender-male-female-variant"
                          :items="Gender"
                          color="white"
                          v-model="gender"
                          required
                        ></v-select>
                        <v-text-field
                          label="Email"
                          name="Email"
                          prepend-icon="mdi-email"
                          type="text"
                          color="white"
                          v-model="email"
                          required
                        ></v-text-field>
                        <v-select
                          label="Institute"
                          name="Institue"
                          prepend-icon="mdi-school"
                          :items="items"
                          color="white"
                          v-model="institute"
                          required
                        ></v-select>
                      </v-form>
                    </v-card-text>
                    <div class="text-center mt-3">
                      <v-btn rounded dark>CREATE ACCOUNT</v-btn>
                    </div>
                  </v-col>
                  <v-col cols="12" md="4">
                    <v-card-text class="white--text mt-12">
                      <h1 class="text-center display-1">Welcome Back!</h1>
                      <h3 class="text-center">Please Sign Up to Continue</h3>
                    </v-card-text>
                    <div class="text-center">
                      <v-btn rounded outlined dark @click="step--">SIGN IN</v-btn>
                    </div>
                  </v-col>
                </v-row>
              </v-window-item>
            </v-window>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>
<script>
export default {
  data: () => ({
    step: 1,
    items: ["IIT BHU", "IIT Bombay", "IIT Madras", "IIT Delhi"],
    Gender: ["Male", "Female", "Others"],
    Email: "",
    password: "",
    firstname: "",
    lastname: "",
    email: "",
    institute: "",
    gender: "",
  }),
  props: {
    source: String,
  },
};
</script>
<style scoped>
.sin {
  background-image: url("https://images.pexels.com/photos/735911/pexels-photo-735911.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=650&w=940");
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  opacity: 0.8;
}
.cin {
  background-image: url("https://images.pexels.com/photos/943096/pexels-photo-943096.jpeg?auto=compress&cs=tinysrgb&dpr=1&w=500");
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  opacity: 0.7;
}
</style>