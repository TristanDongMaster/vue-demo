<template>
   <li>
      {{ title }}
      <button v-on:click="update">clear</button>
   </li>
</template>

<script>
/* eslint-disable */
export default {
  name: 'Sync',
  props: {
    title: String
  },
  methods:{
      update(){
          this.$emit('update:title', 'clear')
      }
  }
}
</script>
