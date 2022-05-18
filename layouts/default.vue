<template>
  <v-app dark class="app__background">
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar
      class="app__bar "
      style="background-color: black"
      :clipped-left="clipped"
      fixed
      app
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer"  class="hidden-sm-and-up"/>
      <v-row>
        <v-col md="1" class="ml-md-5">
          <v-avatar>
            <v-img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSVshzdcGmdMfhqcyq3m2Sl94tFahUwlpbvhw&usqp=CAU"></v-img>
          </v-avatar>
        </v-col>
        <v-col md="2" class="pt-md-6">
          <v-toolbar-title v-text="title" />
        </v-col>
      </v-row>
      <v-spacer />
    </v-app-bar>
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
    <v-footer
      class="app__footer"
      :absolute="!fixed"
      app
    >
      <v-row>
        <v-col offset-md="5">
          <span>&copy; {{ new Date().getFullYear() }} / Jonathan Malagueta - Fullstack Developer</span>
        </v-col>
      </v-row>
    </v-footer>
  </v-app>
</template>

<script lang="ts">
export default {
  name: 'DefaultLayout',
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: true,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/'
        }
      ],
      miniVariant: false,
      rightDrawer: false,
      view: window.screen.width,
      title: 'LofiJon'
    }
  },
  methods: {

  }
}
</script>

<style scoped>
  .app__bar {
    background-color: #18181A;
  }

  .app__background {
    background-image: url("https://wallpaperxyz.com/wp-content/uploads/Gif-Animated-Wallpaper-Background-Full-HD-Free-Download-for-PC-Macbook-261121-Wallpaperxyz.com-29.gif");
  }

  .app__footer {
    background-color: transparent;
  }
</style>
