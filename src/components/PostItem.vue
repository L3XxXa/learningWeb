<template>
    <div class="post">
        <div>
            <div><strong>{{post.title}}</strong></div>
            <div><strong>Body:</strong> {{post.body}}</div>
        </div>
        <div class="post_btns">
            <my-button style="border-color: red" @click="$emit('remove', post)">Delete</my-button>
        </div>
    </div>
</template>

<script>
    export default{
        props:{
            post:{
                type: Object,
                required: true
            }
        }
    }
</script>

<style>
    .post{
        padding: 15px;
        border: 4px solid blueviolet;
        margin-top: 10px;
        font-size: 20px;
        display: flex;
        align-items: center;
        justify-content: space-between;
    }   
</style>