<template>
    <div>
        <span> custom input:</span>
        <input
        v-bind:value="value"
        v-on:input="$emit('input', $event.target.value)"
        >
    </div>
</template>

<script>
/* eslint-disable */
export default {
    name: 'CustomInput',
    props: ['value'],
}
</script>
