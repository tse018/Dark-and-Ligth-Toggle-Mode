<template>
   <div :class="mode">
      <Header :mode="mode" @toggle="toggle" />
   </div>
</template>

<script>
import Header from "../components/Header.vue";

export default {
   data() {
      return {
         mode: "ligth",
      };
   },

   components: {
      Header,
   },

   methods: {
      toggle() {
         if (this.mode === 'ligth') {
            this.mode = 'dark'
         } else {
            this.mode = 'ligth'
         }
      }
   }
};
</script>

<style>
</style>
