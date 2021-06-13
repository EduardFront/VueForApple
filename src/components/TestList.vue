<template>
  <div class="List">
    {{TestList}}
  </div>
</template>

<script>
import db from './db'

export default {
  name:'TestList',
  data(){
    return{
      TestList:  []
    };

  },
  async mounted() {
    this.TestList = await db.Get("Test?",[[]])
  }
};
</script>

<style>

</style>