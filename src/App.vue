<template>
  <v-app id="inspire">
    <v-navigation-drawer class="bg-gray-100 py-6 flex flex-col justify-center sm:py-12"
      style="background-image: url('https://picsum.photos/id/1018/1000')" v-model="drawer" :mobile-breakpoint="768" app>
      <v-img class="pa-4 pt-7 " src="" height="170">
        <v-avatar size="70" class="mb-2">
          <img src="mountains.jpg" alt="Sakhile Simelane">
        </v-avatar>
        <div class="gray--text text-subtitle-1 font-weight-bold">
          Sakhile Simelane
        </div>

      </v-img>

      <v-list dense nav>
        <v-list-item v-for="item in items" :key="item.title" :to="item.to" link>
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar app color="primary" class="bg-gradient-to-r from-gray-100 to-gray-300" prominent
      :height="$route.path === '/' ? '238' : '170'">
      <template v-slot:img="{ props }">
        <v-img v-bind="props"></v-img>
      </template>

      <v-container class="header-container pa-0
      ">
        <v-row>
          <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
          <v-spacer></v-spacer>
          <search />
        </v-row>
        <v-row>
          <v-toolbar-title class="text-h4 ml-4">
            {{ $store.state.appTitle }}
          </v-toolbar-title>
        </v-row>
        <v-row>
          <live-date-time />
        </v-row>
        <v-row v-if="$route.path === '/'">
          <field-add-task />
        </v-row>
      </v-container>

    </v-app-bar>

    <v-main>
      <router-view></router-view>
      <snackbar />
    </v-main>
  </v-app>
</template>

<script>
export default {
  data: () => ({
    drawer: null,
    items: [
      { title: 'Todo', icon: 'mdi-format-list-checks', to: '/' },
      { title: 'About', icon: 'mdi-help-box', to: '/about' },
    ],
  }),
  mounted() {
    this.$store.dispatch('getTasks')
  },
  components: {
    'search': require('@/components/Tools/Search.vue').default,
    'live-date-time': require('@/components/Tools/LiveDateTime.vue').default,
    'field-add-task': require('@/components/Todo/FieldAddTask.vue').default,
    'snackbar': require('@/components/Shared/Snackbar.vue').default
  }
}
</script>

<style lang="sass">
  .header-container
    max-width: none
</style>