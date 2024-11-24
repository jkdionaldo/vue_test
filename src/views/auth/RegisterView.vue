<script setup>
import AppLayout from "@/components/layout/AppLayout.vue";

//For pass verification
import { ref } from "vue";

const rules = {
  required: (value) => !!value || "Required.",
  min: (v) => v.length >= 8 || "Min 8 characters",
  emailMatch: () => `The email and password you entered don't match`,
};

const show1 = ref(false);
const show2 = ref(true);
const password = ref("Password");

//for eye

const visible = ref(false);
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
              <!--<v-image src="/logo.png" width="50"></v-image>-->
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
                  :rules="[rules.required, rules.min]"
                  hint="At least 8 characters"
                  name="input-10-1"
                  counter
                  @click:append="show1 = !show1"
                ></v-text-field>

                <v-text-field
                  label="Password"
                  :append-inner-icon="visible ? 'mdi-eye' : 'mdi-eye-off'"
                  :type="visible ? 'text' : 'password'"
                  placeholder="Enter your password"
                  @click:append-inner="visible = !visible"
                  :rules="[rules.required, rules.min]"
                  hint="At least 8 characters"
                  name="input-10-1"
                  counter
                  @click:append="show1 = !show1"
                ></v-text-field>

                <v-btn
                  class="my-4"
                  type="Register"
                  append-icon="mdi-account-plus-outline"
                  block
                  >Register</v-btn
                >

                <h6 class="my-3 text-center">
                  Already have an account?
                  <RouterLink
                    to="/"
                    class="text-primary"
                    style="text-decoration: none"
                    >Back to Login<v-icon icon="mdi-chevron-right"></v-icon
                  ></RouterLink>
                </h6>
              </v-form>
            </v-sheet>
          </v-card>
        </v-col>
      </v-row>
    </template>
  </AppLayout>
</template>
