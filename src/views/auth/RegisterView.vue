<script setup>
import AppLayout from "@/components/layout/AppLayout.vue";
</script>

<template>
  <AppLayout>
    <template #content>
      <v-row>
        <v-col cols="12" md="6" class="mx-auto">
          <v-card
            class="mx-auto"
            width="100%"
            elevation="24"
            style="margin-top: 10%"
          >
            <v-card-title class="text-center">
              <v-image src="/logo.png" width="50"></v-image>
              <h4 class="font-weight-black text-center">Cam'n Go</h4>
              <small>Register Form</small>
            </v-card-title>

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

                <v-btn
                  class="my-4"
                  type="Register"
                  append-icon="mdi-account-plus-outline"
                  block
                  >Register</v-btn
                >

                <divider class="my-4"></divider>
                <h6 class="my-3 text-center">
                  Already have an account?
                  <RouterLink to="/" class="text-primary"
                    >Back to Login</RouterLink
                  >
                </h6>
              </v-form>
            </v-sheet>
          </v-card>
        </v-col>
      </v-row>
    </template>
  </AppLayout>
</template>
