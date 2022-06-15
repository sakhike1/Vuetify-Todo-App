<template>

  <div class="about pa-10
  ">

    <h1>About {{ $store.state.appTitle }} </h1>

    <p>Vuex is a state management pattern + library for Vue.js applications. It serves as a centralized store for all
      the components in an application, with rules ensuring that the state can only be mutated in a predictable fashion
    </p>
    <p>Vuetify comes with a built-in layout system that just works out of the box. Components such as v-app-bar and
      v-footer support a special property named app. This property tells Vuetify that the corresponding component is
      part of your application’s layout</p>
    <p> Tailwind has beautifully designed, expertly crafted components that follow all accessibility best practices and
      are
      easy to
      customize</p>
    <p> You can filter task on the search option, you can add date, edit task, delete task, set dates and sort items,
      if you refresh the page task remains on the page
    </p>
  </div>
</template>



<style>
.v-main__wrap {
  background-image: bg-gradient-to-r from-gray-100 to-gray-300;
}
</style>
