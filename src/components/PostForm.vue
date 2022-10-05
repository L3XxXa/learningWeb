<template>
    <div>
        <h4>
            Make new post
        </h4>
        <form @submit.prevent>
            <my-input
                v-model="post.title"
                type="text"
                placeholder="Post name"/>

            <my-input 
                v-model="post.body"
                type = "text"
                placeholder="Body"/>
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

    h4{
        font-size: 40px;
    }
    .empty{
        margin-top: 60px;
    }
</style>