<template>
  <v-list class="pt-0" flat>

    <draggable v-model="tasks" handle=".handle">
      <task v-for="task in tasks" :key="task.id" :task="task" />
    </draggable>
  </v-list>
</template>

<script>
import draggable from 'vuedraggable'

export default {
  computed: {
    tasks: {
      get() {
        return this.$store.getters.tasksFiltered
      },
      set(value) {
        this.$store.dispatch('setTasks', value)
      }
    }
  },
  components: {
    'task': require('@/components/Todo/Task.vue').default,
    draggable
  }
}
</script>

<style>
.v-application .blue.lighten-5 {
  background-color: #F5F5F7 !important;
  border-color: #E3F2FD !important;

}
</style>