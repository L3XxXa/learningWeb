<template>
      <input :value="modelValue" @input="updateInput" class="input" type="text">
</template>

<script>
    export default {
      name: 'my-input',
      props: {
        modelValue: [String, Number]
      },
      methods: {
        updateInput(event) {
          this.$emit('update:modelValue', event.target.value)
        }
      }
    }
    </script>

<style scoped>
    .input{
      padding: 15px;
      border: 3px solid blueviolet;
      margin-top: 10px;
      font-size: 20px;
      width: 100%;
    }
</style>