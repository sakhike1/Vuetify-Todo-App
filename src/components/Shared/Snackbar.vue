<template>
  <v-snackbar v-model="$store.state.snackbar.show">
    {{ $store.state.snackbar.text }}

    <template v-slot:action="{ attrs }">
      <v-btn @click="$store.commit('hideSnackbar')" text v-bind="attrs">
        Close
      </v-btn>
    </template>
  </v-snackbar>
</template>

<script>
export default {};
</script>

<style>
.v-snack__content {
  flex-grow: 1;
  font-size: 0.875rem;
  font-weight: 400;
  letter-spacing: 0.0178571429em;
  line-height: 1.25rem;
  margin-right: auto;
  padding: 14px 16px;
  text-align: initial;
  background: #F9FBE7;
  color: black;

}

.v-snack__wrapper.theme--dark {
  background-color: #2cf105;
  color: rgba(255, 255, 255, 0.87);
}
</style>
