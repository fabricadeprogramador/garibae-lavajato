<template>
  <v-app>
    <v-app-bar app>
     <v-btn @click=back text icon v-if="$route.path != '/'">
         <v-icon >
           mdi-arrow-left
         </v-icon>
       </v-btn>
       <v-app-bar-nav-icon v-else @click="drawer = !drawer"></v-app-bar-nav-icon>       
      <v-toolbar-title class="headline text-uppercase">
        
        <span>Home</span>
        
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn
        text
        icon
        to="/solicitacoes"
      >
      <v-icon>
        mdi-bell
      </v-icon>
       
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
           <v-list-item-avatar>
              <v-img src="https://randomuser.me/api/portraits/women/85.jpg"></v-img>
            </v-list-item-avatar>
            <v-list-item-content>
            <v-list-item-title class="title">Empresa </v-list-item-title>
          </v-list-item-content>
        </v-list-item>
          <v-list-item>
            <v-list-item-title>Solicitações</v-list-item-title>
          </v-list-item>
          <v-list-item>
            <v-list-item-title>Serviços</v-list-item-title>
          </v-list-item>
        <v-list-item>
          <v-list-item-title>Historias serviços</v-list-item-title>
        </v-list-item>
        <v-list-item>
          <v-list-item-title>Sair</v-list-item-title>
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
    back(){
      history.back(-1)
    }
  },
  watch: {
    group () {
      this.drawer = false
    },
  },
};
</script>

<style>
  *{
    font-family: 'Ubuntu', sans-serif;
  }
</style>