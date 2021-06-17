<template>
  <div class="List">
    <TestView v-for="(Test, index) in TestList.data" :key = "index" v-bind:Test="Test"/>
  </div>
</template>

<script>
import db from './db'
import TestView from "./TestView"

export default {
  name:'TestList',
  data(){
    return{
      TestList:  []
    };

  },
  async mounted() {
    this.TestList = await db.Get("Test?",[[]])
  },
  components: {
    TestView
  }
};
</script>

<style>

</style>