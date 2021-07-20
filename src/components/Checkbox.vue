<template>
  <div>
    <label :for="labelfor">{{ labelText }}</label>
    <input
      type="checkbox"
      :name="inputName"
      :id="inputId"
      :value="inputValue"
      @change="$emits('update:field', !field)"
    />
  </div>
</template>

<script>
export default {
  emits: ["update:field"],
  props: {
    labefor: {
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
  },
};
</script>

<style>
</style>