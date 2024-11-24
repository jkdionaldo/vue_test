<!--Programming naming conventions-->

<script setup>
import AppLayout from "@/components/layout/AppLayout.vue";
import { useDisplay } from "vuetify";
import "@/assets/login_style.css";

const { mobile } = useDisplay();

import { ref } from "vue";

const visible = ref(false);
</script>

<template>
  <AppLayout>
    <template #content>
      <v-row class="">
        <v-col cols="12" md="6" class="mx-auto" style="margin-top: 10%">
          <v-card elevation="24" class="mx-auto" width="100%">
            <v-card-title class="text-center">
              <!--
              <v-image
                src="/logo.png"
                :width="mobile ? '75%' : '25%'"
                width="50"
              ></v-image>
              -->
              <h4 class="font-weight-black text-center">Cam'n Go</h4>
              <small>Login</small>
            </v-card-title>

            <v-sheet class="mx-auto" width="85%">
              <v-form fast-fail @submit.prevent>
                <v-text-field
                  clearable
                  label="Username"
                  placeholder="Enter your Username"
                  persistent-clear
                  prepend-inner-icon="mdi-email-outline"
                ></v-text-field>

                <v-text-field
                  label="Password"
                  :append-inner-icon="visible ? 'mdi-eye' : 'mdi-eye-off'"
                  :type="visible ? 'text' : 'password'"
                  placeholder="Enter your password"
                  prepend-inner-icon="mdi-lock-outline"
                  @click:append-inner="visible = !visible"
                ></v-text-field>

                <v-class class="d-flex justify-space-between">
                  <label class="checkbox-container">
                    <input class="custom-checkbox" type="checkbox" />
                    <span class="checkmark"></span>
                    <small>Remember Me</small>
                  </label>
                  <h6 class="text-right">Forgot Password?</h6>
                </v-class>

                <v-btn class="mt-2" type="Login" prepend-icon="mdi-login" block
                  >Login</v-btn
                >
              </v-form>

              <v-divider class="my-4"></v-divider>
              <h6 class="my-3 text-center">
                Don't have an account?
                <RouterLink
                  to="/register"
                  class="text-primary"
                  style="text-decoration: none"
                  >Sign up here<v-icon icon="mdi-chevron-right"></v-icon
                ></RouterLink>
              </h6>
            </v-sheet>
          </v-card>
        </v-col>
      </v-row>
    </template>
  </AppLayout>
</template>
