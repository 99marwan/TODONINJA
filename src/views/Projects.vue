<template>
  <div class="projects">
    <h3 class="subheading grey--text ma-2">Projects</h3>
    <!--keep thing sin centre-->
    <v-container class="my-5">
      <v-expansion-panels>
    <v-expansion-panel v-for="project in myProjects" :key="project.title">
      <v-expansion-panel-header>
        {{project.title}}
      </v-expansion-panel-header>
      <v-expansion-panel-content class="px-4 grey--text">
         <div class="font-weight-bold">Due by {{ project.due }}</div>
              <div>{{ project.content }}</div>
      </v-expansion-panel-content>
    </v-expansion-panel>
  </v-expansion-panels>
    </v-container>
  </div>
</template>

<script>



export default {
  name: 'Projects',
  data() {
    return {
      projects: [
        { title: 'Design a new website', person: 'The Net Ninja', due: '1/1/2019', status: 'ongoing', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'},
        { title: 'Code up the homepage', person: 'Chun Li', due: '10/1/2019', status: 'complete', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'},
        { title: 'Design video thumbnails', person: 'Ryu', due: '20/12/2018', status: 'complete', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'},
        { title: 'Create a community forum', person: 'Gouken', due: '20/10/2018', status: 'overdue', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'},
        { title: 'Design a new website..again', person: 'The Net Ninja', due: '1/1/2019', status: 'ongoing', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'}
      ]
    }
  },
  computed: {
    myProjects() {
      return this.projects.filter(project => {
        return project.person === 'The Net Ninja' && project.status != 'complete'
      })
    }
  }
 
}
</script>
