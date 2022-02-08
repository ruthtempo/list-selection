<template>
  <div id="app">
    <List
      @onselection=displaySelection
      :selection="selected"
      :list="fruta"
    />
    <List @onselection=displaySelection 
      :selection="selected"
      :list="fruits"
     />
    {{selected}}
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import List from './components/List.vue';

export default Vue.extend({
  name: 'App',
  components: {
    List
  }, 
  data(){
    return{
      selected:[] as string[],
      fruta:['mango', 'dragonfruit', 'lime'],
      fruits:['banana', 'mango', 'strawberry', 'dragonfruit', 'lichy', 'coconut'],
    }
  },
  methods:{
    displaySelection(arr: string[]){
      this.selected = arr
    }
  }
});
</script>

<style>

</style>
