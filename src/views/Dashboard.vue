<template>
  <div class="home">
    <h3  class=" grey--text ma-2">Dashboard</h3>
        <!--keep thing sin centre-->
    <v-container class="my-5 ">
     <v-row class="mb-3">
     <v-tooltip top>
          <template v-slot:activator="{ on, attrs }">
          <v-btn small text color="grey" @click="sortBy('title')"  v-bind="attrs"
          v-on="on">
            <v-icon small left>folder</v-icon>
            <span class="caption text-lowercase">By project name</span>
          </v-btn>
          </template>
          <span>Sort by project name</span>
        </v-tooltip>

        <v-tooltip top>
         <template v-slot:activator="{ on, attrs }">
          <v-btn small text color="grey" @click="sortBy('person')" v-bind="attrs"
          v-on="on">
            <v-icon small left>person</v-icon>
            <span class="caption text-lowercase">By Person</span>
          </v-btn>
         </template>
          <span>Sort by project author</span>
        </v-tooltip>
     </v-row>
     
     
      <v-row no-gutters v-for="project in projects" :key="project.title">
      <v-col
       cols="6"
       :class="`pa-3 project ${project.status}`"
      >
        <v-card
          class="pa-3"
          flat
        >
          <div class="caption grey--text">Project title</div>
            <div>{{ project.title }}</div>
        </v-card>
      </v-col>
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
       <v-col
        cols="2"
        
      >
        <v-card
          class="pa-3"
          flat
        >
          <div class="caption grey--text">Due by</div>
            <div>{{ project.due }}</div>
        </v-card>
      </v-col>
       <v-col
        cols="2"
        
      >
        <v-card
          class="pa-3"
          flat
        >
        
          <div class="caption grey--text">Status</div>
            <div>{{ project.status }}</div>
        </v-card>
      </v-col>
    </v-row>
    </v-container>
  </div>
</template>

<script>



export default {
  name: 'Dashboard',
   data() {
    return {
      projects: [
        { title: 'Design a new website', person: 'The Net Ninja', due: '1/1/2019', status: 'ongoing', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'},
        { title: 'Code up the homepage', person: 'Chun Li', due: '10/1/2019', status: 'complete', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'},
        { title: 'Design video thumbnails', person: 'Ryu', due: '20/12/2018', status: 'complete', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'},
        { title: 'Create a community forum', person: 'Gouken', due: '20/10/2018', status: 'overdue', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'},
      ]
    }
  },
  methods: {
    sortBy(prop) {
      this.projects.sort((a,b) => a[prop] < b[prop] ? -1 : 1)
    }
  }
}
</script>

<style>
.project.complete{
  border-left: 4px solid #3CD1C2;
}
.project.ongoing{
  border-left: 4px solid orange
}
.project.overdue{
  border-left: 4px solid tomato;
}
</style>