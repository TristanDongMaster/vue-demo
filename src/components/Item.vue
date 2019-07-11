<template>
   <li>
      {{ title }}
      <button v-on:click="$emit('remove')">Remove</button>
   </li>
</template>

<script>
export default {
  name: 'Item',
  props: {
    title: String
  }
}
</script>
