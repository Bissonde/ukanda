<template>
  <router-view />
</template>

<script setup>
//
// const activeColor = ref('red')
// const fontSize = ref(30)
</script>

<!-- <script>
import HelloWorld from './components/HelloWorld';

export default {
  name: 'App',

  components: {
    HelloWorld,
  },
  data: () => ({

  }),
};
</script> -->


<style lang="sass">
  .v-input.expanding-search
    .v-input__slot 
      &:before, &:after
        border-color: transparent !important
    &:closed  
        max-width: 43px
</style>