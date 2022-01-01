<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark
    >
      <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
          transition="scale-transition"
          width="40"
        />

        <v-img
          alt="Vuetify Name"
          class="shrink mt-1 hidden-sm-and-down"
          contain
          min-width="100"
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-name-dark.png"
          width="100"
        />
      </div>

      <v-spacer></v-spacer>

      <v-btn
        href="https://github.com/vuetifyjs/vuetify/releases/latest"
        target="_blank"
        text
      >
        <span class="mr-2">Home</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar>
    <NavBar/>
    <v-container>
      <v-navigation-drawer v-show="isShow" permanent expand-on-hover>
        <v-list-item >
          <v-list-item-content>
            <v-list-item-title class="text-h6">
              Manager
            </v-list-item-title>
            <v-list-item-subtitle>
              Empower your managing
            </v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>
        <v-divider></v-divider>

        <v-list
          dense
          nav
        >
          <v-list-item
            v-for="item in items"
            :key="item.title"
            link
          >
            <v-list-item-icon>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-item-icon>

            <v-list-item-content>
              <v-list-item-title>{{ item.title }}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list>
    </v-navigation-drawer>
    </v-container>
    <v-button @click="isShow =! isShow"> Manager?</v-button>
 <Home/>
  </v-app>
</template>

<script>
import Home from './components/Home';
import NavBar from './components/NavBar';
  export default {
    name: 'App',
    components: {
    Home,
    NavBar,
  },
    data () {
      return {
        isShow: true,
        items: [
          { title: 'Dashboard', icon: 'mdi-view-dashboard' },
          { title: 'Photos', icon: 'mdi-image' },
          { title: 'Manage Team', icon: 'mdi-account-group-outline'},
          { title: 'Manage Transaction', icon: 'mdi-cash-multiple'}
        ],
        right: null,
      }
    },
  }
</script>
