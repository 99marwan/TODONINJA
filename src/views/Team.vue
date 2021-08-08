<template>
  <div class="team">
    <h3  class="subheading grey--text ma-2">Team</h3>
        <!--keep thing sin centre-->
    <v-container class="my-5">
     <v-row no-gutters >
      <v-col
       cols="4"
       v-for="person in team" :key="person.name"
      >
        <v-card class="subtitle-2 text-center  ma-3">
          <v-responsive class="pt-4">
            <v-avatar size="100" class="grey lighten-2">
              <img :src="person.avatar">
            </v-avatar>
          </v-responsive>
           <v-card-text>
              <div class="subheading">{{ person.name }}</div>
              <div class="grey--text">{{ person.role }}</div>
            </v-card-text>
            <v-card-actions>
              <v-btn text color="grey">
                <v-icon small left>message</v-icon>
                <span class="">Message</span>
              </v-btn>
            </v-card-actions>
        </v-card>
      </v-col>
      <!--
      <v-col
        cols="2"
      >
        <v-card
          class="pa-3"
          flat
        >
          <div class="caption grey--text">Person</div>
            <div>{{ project.person }}</div>
        </v-card>
      </v-col>
       -->
    </v-row>
    </v-container>
  </div>
</template>

<script>



export default {
  name: 'Team',
  data() {
    return {
      team: [
         { name: 'The Net Ninja', role: 'Web developer', avatar: '/avatar-1.png' },
        { name: 'Ryu', role: 'Graphic designer', avatar: '/avatar-2.png' },
        { name: 'Chun Li', role: 'Web developer', avatar: '/avatar-3.png' },
        { name: 'Gouken', role: 'Social media maverick', avatar: '/avatar-4.png' },
        { name: 'Yoshi', role: 'Sales guru', avatar: '/avatar-5.png'}
      ]
    }
  }
 
}
</script>
