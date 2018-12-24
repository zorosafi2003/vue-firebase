<template>
  <v-app>
    <v-navigation-drawer app v-model="sideNav">
      <v-list>
        <v-list-tile v-for="item in menuItems" v-bind:key="item.title">
          <v-list-tile-action>
            <v-icon>{{item.icon}}</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>{{item.title}}</v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar  app dark class="purple darken-1">
      <v-toolbar-side-icon @click.native="sideNav =!sideNav"></v-toolbar-side-icon>
      <v-toolbar-title>DevMeetup</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-items class="hidden-sm-and-down">
        <v-btn flat>View Meets</v-btn>
      </v-toolbar-items>
    </v-toolbar>

    <v-content>
      <v-container fluid>
        <router-view></router-view>
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      sideNav: false,
      menuItems: [
        { icon: "supervisor_account", title: "View Meetups" },
        { icon: "room", title: "Organize Meetup" },
        { icon: "person", title: "Profile" },
        { icon: "face", title: "Sign up" },
        { icon: "lock", title: "Sign in" }
      ]
    };
  }
};
</script>
