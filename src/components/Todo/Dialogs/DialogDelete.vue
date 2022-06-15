<template>
  <v-dialog :value="true" persistent max-width="290">
    <v-card class="bg-gradient-to-r from-rose-100 to-teal-100">
      <v-card-title class="text-h5"> Delete task ? </v-card-title>
      <v-card-text>Are you sure you want to delete this task</v-card-text>
      <v-card-actions>
        <v-spacer></v-spacer>
        <v-btn @click="$emit('close')" color="red" text> No </v-btn>
        <v-btn
          @click="$store.dispatch('deleteTask', task.id)"
          color="green"
          text
        >
          Yes
        </v-btn>
      </v-card-actions>
    </v-card>
  </v-dialog>
</template>

<script>
export default {
  props: ["task"],
};
</script>

<style></style>
