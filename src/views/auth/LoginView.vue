<!--Programming naming conventions-->

<script setup>
import AppLayout from "@/components/layout/AppLayout.vue";
import { useDisplay } from "vuetify";

const { mobile } = useDisplay();
</script>

<template>
  <AppLayout>
    <template #content>
      <v-row>
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
                ></v-text-field>

                <v-text-field
                  clearable
                  label="Password"
                  placeholder="Enter your Password"
                  persistent-clear
                ></v-text-field>

                <v-class class="d-flex justify-space-between">
                  <h6>Remember Me</h6>
                  <h6 class="text-right">Forgot Password?</h6>
                </v-class>

                <v-btn class="mt-2" type="Login" prepend-icon="mdi-login" block
                  >Login</v-btn
                >
              </v-form>

              <v-divider class="my-4"></v-divider>
              <h6 class="my-3 text-center">
                <RouterLink to="/register" class="text-primary"
                  >Sign up here</RouterLink
                >
              </h6>
            </v-sheet>
          </v-card>
        </v-col>
      </v-row>
    </template>
  </AppLayout>
</template>
