<template>
  <v-app id="inspire">
    <v-navigation-drawer
    v-model="drawer"
      app
      >
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title class="text-h6">
            To-Do
          </v-list-item-title>
          <v-list-item-subtitle>
            List
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
          :to="item.to"
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

    <!-- <v-app-bar app>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-toolbar-title>To-Do List</v-toolbar-title>
    </v-app-bar> -->

        <v-app-bar
      app
      prominent
      color="teal lighten-3"
      dark
      src="https://s2.glbimg.com/gR7AqZNmjOBbdN79GNK6OAPzX2c=/940x523/e.glbimg.com/og/ed/f/original/2019/04/18/rotina.jpg"
    >
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-toolbar-title>Title</v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-heart</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-dots-vertical</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main>
      <router-view />
    </v-main>
  </v-app>
</template>

<script>
  export default {
    data: () => ({ 
      drawer: null,
              items: [
          { title: 'Tarefas', icon: 'mdi-view-dashboard', to:'/' },
          { title: 'Sobre', icon: 'mdi-help-box', to:'/sobre' },
        ],
    }),
  }
</script>