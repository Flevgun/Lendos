<template>
  <select name="selectName" @change="$emit('update:field', $event.target.value)">
    <option
      v-for="option in options"
      :key="option.id"
      :value="`value-${option.id}`"
    >
      {{ option.name }}
    </option>
  </select>
</template>

<script>
export default {
    props: {
        field: {
            type: String,
            required: true
        },
        options: {
            type: Array,
            requierd: true
        },
        selectName: {
            type: Array,
            requierd: true
        },
    }
}
</script>

<style>
</style>