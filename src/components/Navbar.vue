<template>
  <div class="navbar">
    <v-app-bar flat color="primary" dark>
      <v-app-bar-nav-icon @click="drawer = true" class="d-flex d-sm-none"></v-app-bar-nav-icon>

      <v-toolbar-title>FoodPanda</v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn class="mr-2 d-none d-sm-flex" text outlined v-for="(item, index) in items" :key="index">
        <v-icon class="mr-2">{{ item.icon }}</v-icon>
        <span class="d-none d-sm-none d-md-flex">{{ item.title }}</span>
      </v-btn>

    </v-app-bar>
    <v-navigation-drawer color="primary" dark disable-resize-watcher v-model="drawer" absolute temporary>
      <v-list-item>
        <v-list-item-avatar>
          <v-img src="https://randomuser.me/api/portraits/men/78.jpg"></v-img>
        </v-list-item-avatar>

        <v-list-item-content>
          <v-list-item-title>John Leider</v-list-item-title>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list dense>

        <v-list-item v-for="item in items" :key="item.title" link>
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>

        </v-list-item>
      </v-list>
      <template v-slot:append>
        <div class="pa-2">
          <v-btn text outlined block>Logout</v-btn>
        </div>
      </template>

    </v-navigation-drawer>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        drawer: null,
        items: [
          { title: 'Home', icon: 'mdi-home' },
          { title: 'Cart', icon: 'mdi-cart' },
          { title: 'Wishlist', icon: 'mdi-heart' },
          { title: 'Orders', icon: 'mdi-food' },
          { title: 'Account', icon: 'mdi-account' },
        ],
      }
    },
  }
</script>