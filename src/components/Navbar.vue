<template> 
  <nav >
    <v-app-bar flat app dark>
      <!--three lines new -->
      <v-app-bar-nav-icon @click="drawer = !drawer" class="grey--text"></v-app-bar-nav-icon>
      <v-toolbar-title class="text-uppercase grey--text">
        <span class="font-weight-light">Todo</span>
        <span>Ninja</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>

      
      <!--dropdown menue-->
      <template>
        <div class="text-center" >
          <v-menu offset-y>
            <template v-slot:activator="{ on, attrs }">
              <v-btn
                text
                color="grey"
                v-bind="attrs"
                v-on="on"
              >
                <v-icon left>expand_more</v-icon>
                <span>Menu</span>
              </v-btn>
            </template>
            <v-list>
            `<v-list-item v-for="link in links" :key="link.text" router :to="link.route">
              <v-list-item-action>
                <v-icon>{{link.icon}}</v-icon>
              </v-list-item-action>
              <v-list-item-title>{{link.text}}</v-list-item-title>
            </v-list-item>
            </v-list>
          </v-menu>
        </div>
    </template>


      <v-btn text color="grey">
        <span>Sign Out</span>
        <v-icon right>exit_to_app</v-icon>
      </v-btn>
    </v-app-bar>

    <v-navigation-drawer app v-model="drawer" class="primary">
       <v-row class="text-center">
        <v-col class="mt-5">
          <v-avatar size="100">
            <img class="text-lg-center" src="/avatar-1.png">
          </v-avatar>
          <p class="white--text subheading mt-1">The Net Ninja</p>
        </v-col>
       </v-row>
       <v-col>
        <Popup />
       </v-col>
      <v-list>
        <v-list-item v-for="link in links" :key="link.text" router :to="link.route">
            <v-list-item-action>
            <v-icon class="white--text">{{link.icon}}</v-icon>
            </v-list-item-action>
            <v-list-item-title class="white--text">{{link.text}}</v-list-item-title>
        </v-list-item>
        
      </v-list>
    </v-navigation-drawer>

  </nav>
</template>

<script>
import Popup from './Popup'
export default {
  components: {Popup},
  data() {
    return {
      drawer: false,
      links: [
        { icon: 'dashboard', text: 'Dashboard', route: '/' },
        { icon: 'folder', text: 'My Projects', route: '/projects' },
        { icon: 'person', text: 'Team', route: '/team' },
      ]
    }
  }
}
</script>

<style>

</style>
