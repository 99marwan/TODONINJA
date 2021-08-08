<!--
<template>
  <v-dialoge v-model="dialog" max-width="600px">
    <template v-slot:activator="{ on, attrs }">
      <v-btn v-bind="attrs" v-on="on" class="success">Add new project</v-btn>
   </template>
    <v-card>
        <v-card-title>
            <h2>Add a new Project</h2>
        </v-card-title>
    </v-card>
  </v-dialoge>
</template>
-->
<template>
  <div class="text-center">
    <v-dialog
      v-model="dialog"
      width="600"
    >
      <template v-slot:activator="{ on, attrs }">
        <v-btn
          color="success"
          v-bind="attrs"
          v-on="on"
        >
          Add new project
        </v-btn>
      </template>

      <v-card>
        <v-card-title class="grey lighten-2">
          Add a new project
        </v-card-title>

        <v-card-text>
            <v-form class="px-3" ref="form">
                <v-text-field label="title" v-model="title" prepend-icon="folder" :rules="inputRules"></v-text-field>
                <v-textarea label="info" v-model="content" prepend-icon="edit" :rules="inputRules"></v-textarea>
                <v-btn text class="success mx-0" @click="submit">Add project</v-btn>

            </v-form>
        </v-card-text>
      </v-card>
    </v-dialog>
  </div>
</template>
<script>
  export default {
   data(){
       return{
           title: '',
           content: '',
           date: new Date().toISOString().substr(0, 10),
           inputRules: [
                v => !!v || 'This field is required',
                v => v.length >= 3 || 'Minimum length is 3 characters'
           ]
       }
   },
   methods: {
       submit(){
           if(this.$refs.form.validate()) {
                 console.log(this.title, this.content,this.date)
      }

       }
   }
  }
</script>

<style>

</style>>