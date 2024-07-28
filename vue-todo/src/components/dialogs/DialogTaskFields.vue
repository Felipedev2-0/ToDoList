<template>
  <div class="text-center pa-4">
    <v-dialog v-model="taskStore.showDialogTaskFields" max-width="400" persistent>
      <!-- <template v-slot:activator="{ props: activatorProps }">
          <v-btn v-bind="activatorProps">
            Open Dialog
          </v-btn>
        </template>
-->

      <v-card prepend-icon="mdi-map-marker" title="Edit Task">

        <v-text-field
        v-model="props.task.title"
        label="Title"></v-text-field>
        <v-text-field
        v-model="props.task.description"
        label="Description"></v-text-field>

        <template v-slot:actions>
          <v-spacer></v-spacer>

          <v-btn variant="elevated"
          color="primary"
          @click="taskStore.updateTask()">
            Ok
          </v-btn>
        </template>
      </v-card>
    </v-dialog>
  </div>
</template>



<script setup>
import { defineProps } from 'vue'
import { useTaskStore } from '@/stores/task';

const taskStore = useTaskStore()

const props = defineProps({
  task: Object
})
</script>