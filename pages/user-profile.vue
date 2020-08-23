<template>
  <div>
    <v-app-bar app color="primary" dark>
      <v-toolbar-title>Профиль пользователя</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn text to="/" exact>выход</v-btn>
    </v-app-bar>
    <v-main>
      <v-container fluid>
        <v-row align="start" justify="center">
          <v-col cols="12" sm="10" md="6">
            <v-card class="mx-auto">
              <v-skeleton-loader
                :loading="loading"
                transition="fade-transition"
                type="list-item-avatar-two-line"
              >
                <v-list-item class="d-flex">
                  <v-list-item-avatar size="96">
                    <img :src="user.imageUrl" alt="Avatar" />
                  </v-list-item-avatar>

                  <v-card-text>
                    <p>{{ user.name }}</p>
                    <p>{{ user.email }}</p>
                  </v-card-text>
                </v-list-item>
              </v-skeleton-loader>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </div>
</template>

<style>
.user-text {
  width: 245px;
}
</style>

<script>
const fetchDataMock = () => {
  const user = {
    imageUrl: '/avatar.jpg',
    name: 'Иван Иванов',
    email: 'example@mail.com',
  }

  return new Promise((resolve) => {
    setTimeout(() => {
      resolve(user)
    }, 2500)
  })
}

export default {
  async fetch() {
    const user = await fetchDataMock()
    this.user = user
    this.loading = false
  },

  data() {
    return {
      loading: true,
      user: {
        imageUrl: '',
        name: '',
        email: '',
      },
    }
  },
}
</script>
