<template>
    <div class="dialog" v-if ="show" @click="hideDialog">
        <div @click.stop="" class="content">
            <slot>
            </slot>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'my-dialog',
        props:{
            show:{
                type: Boolean,
                default: false
            }
        },
        methods: {
            hideDialog(){
                this.$emit("update:show", false)
            }
        },
    }
</script>

<style scoped>
    .dialog{
        top: 0;
        bottom: 0;
        left: 0;
        right: 0;
        background: rgb(0, 0, 0, 0.5);
        position: fixed;
        display: flex;
    }

    .content{
        margin: auto;
        padding: 20px;
        background: white;
    }
</style>