<template>
  <span>
    <!-- navigation drawer for small screens -->
    <v-navigation-drawer app v-model="drawer" class="blue lighten-2" dark disable-resize-watcher>
      <v-list>
        <template v-for="(item, index) in items">
          <!-- TODO: This isnt done -->
          <v-list-item :key="index" :href="item.href">
            <v-list-item-content>
              {{ item.text }}
            </v-list-item-content>
          </v-list-item>
          <v-divider :key="`divider-${index}`"></v-divider>
        </template>
      </v-list>
    </v-navigation-drawer>
    <!-- toolbar drawer for medium to large screens -->
    <v-app-bar app color="blue darken-4" dark>
      <v-app-bar-nav-icon class="hidden-md-and-up" @click="drawer = !drawer"></v-app-bar-nav-icon>
      <v-spacer class="hidden-md-and-up"></v-spacer>
      <v-toolbar-title>{{ appTitle }}</v-toolbar-title>
      <v-btn text class="hidden-sm-and-down">Menu</v-btn>
      <v-spacer class="hidden-sm-and-down"></v-spacer>
      <v-btn text class="hidden-sm-and-down">SIGN IN</v-btn>
      <v-btn color="blue lighten-3" class="hidden-sm-and-down">JOIN</v-btn>
    </v-app-bar>
  </span>
</template>

<script>
export default {
  name: 'AppNavigation',
  data() {
    return {
      appTitle: 'Meal Prep',
      drawer: false,
      items: [
        { icon: 'Email', text: 'Menu', href: 'www.google.com' },
        { icon: 'Email', text: 'Sign In', href: 'www.google.com' },
        { icon: 'Email', text: 'Join', href: 'www.google.com' },
        { icon: 'About', text: 'About', href: '/About'}]
    };
  }
};
</script>

<style scoped></style>
