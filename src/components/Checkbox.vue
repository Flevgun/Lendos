<template>
  <div>
    <label :for="labelfor">{{ labelText }}</label>
    <input
      type="checkbox"
      :name="inputName"
      :id="inputId"
      :value="inputValue"
      :checked="checked"
      @change="$emit('update:field', !field)"
    />
  </div>
</template>

<script>
export default {
  emits: ["update:field"],
  props: {
    labelfor: {
      type: String,
      required: true,
    },
    labelText: {
      type: String,
      required: true,
    },
    inputName: {
      type: String,
      required: true,
    },
    inputId: {
      type: String,
      required: true,
    },
    field: {
      type: String,
      required: true,
    },
    checked: {
      type: Number,
      required: false
    }
  },
};
</script>

<style>
</style>