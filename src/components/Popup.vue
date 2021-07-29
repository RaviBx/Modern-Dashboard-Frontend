<template>
  <v-row justify="center">
    <v-dialog v-model="dialog" persistent max-width="800px">
      <template v-slot:activator="{ on }">
        <v-btn outlined color="teal lighten-3" dark v-on="on">Add New  Project></v-btn>
      </template>
      <v-card-title>
        <span class="headline">New Project</span>
      </v-card-title>
      <v-from class="px-3" ref="from">
        <v-card-text>
          <v-text-filed label="Title" v-model="title" prepend-icon="folder"></v-text-filed>
          <v-textarea label="information" v-model="content" prepend-icon="edit"></v-textarea>
          <v-col cols="12" lg="6">
            <v-menu
              ref="menu1"
              v-model="menu1"
              :close-on-content-click="flase"
              transition="scale-transition"
              offset-y
              max-width="290px"
              min-width="290px"
              >
                <template v-slot:activator={ on }>
                    <v-text-field 
                    v-model="dateFormatted" 
                    label="Date" 
                    hint="MM/DD//YY Format" 
                    prepend-icon="event"
                    blur="date - parseDate(dateFormatted)"
                    
                >

                    </v-text-field>
                </template>
            </v-menu>
          </v-col>
        </v-card-text>
      </v-from>
    </v-dialog>
  </v-row>
</template>