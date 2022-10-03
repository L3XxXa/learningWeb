<template>
    <div>
        <h4>
            Make new post
        </h4>
        <form @submit.prevent>
            <input
                v-model="post.title"
                type="text"
                class="input" 
                placeholder="Post name">

            <input 
                v-model="post.body"
                type = "text"
                class="input"
                placeholder="Body">
        </form>
        <my-button @click="createPost">Post!!!</my-button>
    </div>
    <div class = "empty"></div>
</template>

<script>
export default{
    data(){
        return{
            post:{
                title: '',
                body: ''
            }
        }
    },
    methods: {
    createPost(){
        this.post.id = Date.now();
        this.$emit('createPostEvent', this.post);
        this.post = {
            title:'',
            body: ''
        }
    }
    }
}
</script>

<style scoped>
    form{
        display: flex;
        flex-direction: column;
    }
    .input{
        padding: 15px;
        border: 3px solid blueviolet;
        margin-top: 10px;
        font-size: 20px;
        width: 100%;
    }
    h4{
        font-size: 40px;
    }
    .empty{
        margin-top: 60px;
    }
</style>