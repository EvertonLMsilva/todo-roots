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
                    <img src="../assets/img/logo.png" class="logo-client" alt="logo">
                  </div>
                  <div class="title-login">
                    <h3>Login in to Your Account</h3>
                  </div>
                    <v-text-field v-model="email" :readonly="loading" :rules="[required]" class="mb-2" clearable
                      label="Email" type="text"></v-text-field>

                    <v-text-field v-model="password" :readonly="loading" :rules="[required]" clearable label="Password"
                      placeholder="Enter your password" type="password"></v-text-field>

                    <v-btn :disabled="!email || !password" :loading="loading" block color="success" size="large"
                      type="submit" variant="elevated">
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

<script>
export default {
  data: () => ({
    form: false,
    email: null,
    password: null,
    loading: false,
  }),
  methods: {
    onSubmit() {

      if (!this.email || !this.password) return
      this.loading = true
      setTimeout(() => (this.loading = false), 2000)
    },
    required(v) {
      return !!v || 'Field is required'
    },
  },
}
</script>

<style scoped>
.container-config {
  display: flex;
  justify-content: center;
  align-items: center;
  align-self: center;
  height: 100%;
}

.logo-client {
  width: 250px;
}

.title-login {
  margin: 20px;
  color: #474747;
}

.background-left-down {
  background-color: #e0e0e0;
}

.background-left {
  background-color: #00a2ff;
  height: 600px;
  border-radius: 0 0 150px 0;
  display: flex;
  justify-content: center;
  align-items: center;
}

.background-right {
  background-color: #e0e0e0;
  height: auto;
}

.background-right-inner {
  background-image: url('../assets/img/livro-com-fundo-de-placa-verde.jpg');
  background-repeat: no-repeat, repeat;
  background-size: cover;
  background-color: #11f7ff;
  border-radius: 0 0 0 150px;
  height: 100%;
  font-size: xx-large;
}
</style>
