<template>
  <v-app>
    <v-main>
      <ToDo/>
    </v-main>
  </v-app>
</template>

<script>
import ToDo from './components/ToDo.vue';

export default {
  name: 'App',

  components: {
    ToDo,
  },

  data: () => ({}),
};
</script>
