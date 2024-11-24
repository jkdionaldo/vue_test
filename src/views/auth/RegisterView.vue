<script setup>
import { ref } from "vue";
const theme = ref("dark");

function onClick() {
  theme.value = theme.value === "light" ? "dark" : "light";
}
</script>

<template>
  <v-responsive class="border rounded">
    <v-app :theme="theme">
      <v-app-bar class="px-3">
        <v-spacer></v-spacer>

        <v-btn
          :prepend-icon="
            theme === 'light' ? 'mdi-weather-sunny' : 'mdi-weather-night'
          "
          text="Toggle Theme"
          slim
          @click="onClick"
        ></v-btn>
      </v-app-bar>

      <v-main>
        <v-container>
          <v-row>
            <v-col cols="12" md="6" class="mx-auto">
              <v-card
                class="mx-auto"
                prepend-icon="mdi-account-alert"
                subtitle="Register Now"
                width="70%"
              >
                <template v-slot:title>
                  <span class="font-weight-black">Cam'n Go</span>
                </template>

                <v-sheet class="mx-auto" width="85%">
                  <v-form fast-fail @submit.prevent>
                    <v-text-field
                      clearable
                      label="Firstname"
                      placeholder="Enter your Firstname"
                      persistent-clear
                    ></v-text-field>

                    <v-text-field
                      clearable
                      label="Lastname"
                      placeholder="Enter your Lastname"
                      persistent-clear
                    ></v-text-field>

                    <v-text-field
                      clearable
                      label="Username"
                      placeholder="Enter your Username"
                      persistent-clear
                    ></v-text-field>

                    <v-text-field
                      clearable
                      label="Password"
                      placeholder="Enter your Password"
                      persistent-clear
                    ></v-text-field>

                    <v-text-field
                      clearable
                      label="Confirm Password"
                      placeholder="Re-Type your Password"
                      persistent-clear
                    ></v-text-field>

                    <v-btn class="my-4" type="submit" block>Submit</v-btn>

                    <divider class="my-4"></divider>
                    <h6 class="my-3 text-center">
                      Already have an account?
                      <RouterLink to="/login" class="text-primary"
                        >Back to Login</RouterLink
                      >
                    </h6>
                  </v-form>
                </v-sheet>
              </v-card>
            </v-col>
          </v-row>
        </v-container>
      </v-main>

      <v-footer class="text-center d-flex flex-column" border app
        >2024 - Copyright</v-footer
      >
    </v-app>
  </v-responsive>
</template>
