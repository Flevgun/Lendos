<template>
  <div v-if="!textarea">
    <label :for="inputId">{{ labelText }}</label>
    <input
      :type="inputType"
      :name="inputName"
      :id="inputId"
      @input="$emit('update:field', $event.target.value)"
    />
  </div>
  <div v-else>
    <label :for="inputId">{{ labelText }}</label>
    <textarea
      :name="inputName"
      :id="inputId"
      @input="$emit('update:field', $event.target.value)"
    ></textarea>
  </div>
</template>

<script>
export default {
  emits: ["update:field"],
  props: {
    textarea: {
      type: Boolean,
      required: false,
    },
    labelText: {
      type: String,
      required: true,
    },
    inputType: {
      type: String,
      required: false,
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