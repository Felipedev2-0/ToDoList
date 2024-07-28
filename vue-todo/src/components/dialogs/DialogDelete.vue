<template>
    <div class="text-center pa-4">
      <v-dialog
        v-model="taskStore.showDialogDelete"
        max-width="400"
        persistent
      >
        
  
        <v-card
          
          text="Are you sure you want to delete this task?"
          title="Delete Task"
        >
          <template v-slot:actions>
            <v-spacer></v-spacer>
  
            <v-btn
            color="red"
            variant="elevated"
            @click="taskStore.toggleDelete">
              No
            </v-btn>
  
            <v-btn
            color="red"
            variant="outlined"
             @click="taskStore.deleteTask">
              Yes
            </v-btn>
          </template>
        </v-card>
      </v-dialog>
    </div>
  </template>


<script setup>
import { useTaskStore } from '@/stores/task';

const taskStore = useTaskStore()



</script>