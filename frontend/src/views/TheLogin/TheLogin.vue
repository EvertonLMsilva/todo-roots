<template>
  <v-container class="container-config">
    <v-row align="center" justify="center">
      <v-col cols="12" sm="10">
        <v-card class="elevation-6 mt-10">
          <v-row>
            <v-col cols="12" lg="6" xl="6" class="background-left-down">
              <div class="background-left">
                <v-card-text class="mt-12 text-center">
                  <v-card class="mx-auto px-6 py-8" max-width="344">
                    <div>
                      <img src="@/assets/img/logo.png" class="logo-client" alt="logo">
                    </div>
                    <div class="title-login">
                      <h3>Login in to Your Account</h3>
                    </div>

                    <v-text-field variant="underlined" v-model="data.email" :readonly="data.loading" :rules="[required]"
                      clearable label="Email" type="text" placeholder="Enter your Email"></v-text-field>

                    <v-text-field variant="underlined" v-model="data.password" :readonly="data.loading" :rules="[required]"
                      clearable label="Password" type="password" placeholder="Enter your password"></v-text-field>

                    <v-btn :disabled="!data.email || !data.password" :loading="data.loading" block color="success" size="large"
                      class="mb-2 mt-5" type="submit" variant="elevated" :onclick="() => onSubmit()">
                      Sign In
                    </v-btn>
                  </v-card>
                </v-card-text>
              </div>
            </v-col>
            <v-col cols="12" lg="6" xl="6" class="background-right">
              <div class="background-right-inner">
              </div>
            </v-col>
          </v-row>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script lang="ts">
import { reactive } from 'vue';

export default {
  name: 'TheLogin',

  setup() {
    const data = reactive({
      form: false,
      email: null,
      password: null,
      loading: false,
    });

    const onSubmit = () => {

      if (!data.email || !data.password) return
      data.loading = true;
      console.log(data.email, data.password);

      setTimeout(() => (data.loading = false), 2000)
    };

    const required = (v) => {
      return !!v || 'Field is required'
    };

    return {
      data,
      onSubmit,
      required
    }
  },
}
</script>

<style scoped src="./style.scss" lang="scss" />
