<template>
  <v-app>
    <v-app-bar app>
     
       <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
      <v-toolbar-title class="headline text-uppercase">
        <span>Home</span>
        
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn
        text
       
      >
       
      </v-btn>
    </v-app-bar>
     <v-navigation-drawer
      v-model="drawer"
      app
      temporary
    >
      <v-list
        nav
        dense
      >
        <v-list-item-group
          v-model="group"
          active-class="deep-purple--text text--accent-4"
        >
          <v-list-item>
            <v-list-item-title>Foo</v-list-item-title>
          </v-list-item>

          <v-list-item>
            <v-list-item-title>Bar</v-list-item-title>
          </v-list-item>

          
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>

    <v-content>
      <router-view></router-view>
    </v-content>
  </v-app>

  
</template>

<script>


export default {
  name: 'App',
  components: {
    
  },
  data: () => ({
    drawer: false,
    group: null,
  }),
  methods:{
    
  },
  watch: {
    group () {
      this.drawer = false
    },
  },
};
</script>
