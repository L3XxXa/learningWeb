<template>
    <button class="button">
        <slot></slot>
    </button>
</template>

<script>
    export default{
        name: "my-button"
    }
</script>

<style scoped>
    .button{
        font-size: 20px;
        padding: 10px 20px;
        background-color: white;
        border: 3px solid blueviolet;
    }
</style>