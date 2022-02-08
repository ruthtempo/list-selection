<template>
    <ul>
      <li
        v-for="(element, index) in list"
        :key="index"
        @click="clicked(element)"
        :class="selection.includes(element)? 'clicked' : '' "
      >
        {{element}}
      </li>
  </ul>
</template>

<script>
export default {
  name:"List",
  props:{
    selection: Array,
    list: Array
  },
  methods:{
    clicked(element){
      //to not modify the props value, we make a copy of the original array inside the function
      let arrayCopy = this.selection.slice() 

      if(this.selection.includes(element)){
        arrayCopy = this.selection.filter(e => e !== element)
      }else{
        arrayCopy.push(element)
      }
      this.$emit('onselection', arrayCopy) //we make the value accessible in the parent through the emit
    }
  }
}
</script>
<style scoped>

li{
  margin:10px;
}

.clicked{
  background-color:yellow
}

</style>