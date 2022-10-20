<!--Ya Ded inside-->
<template>
    <div class = "app">
        <my-button @click="showDialog">
            Create post!!!
        </my-button>
        <my-dialog v-model:show="dialogVisible">
            <post-form @createPostEvent="createPost"/>
        </my-dialog>
        <post-list v-bind:posts="posts" @remove="removePost"/>
    </div>
</template>

<script>
    import PostForm from "@/components/PostForm.vue";
    import PostList from "@/components/PostList.vue";
import MyButton from "./components/UI/MyButton.vue";

    export default{
        components: {
    PostForm,
    PostList,
    PostForm,
    MyButton
},
    data(){
        return{
            posts:[
                {id: 1, title: "Hello, world", body: "Lorem ipsum dolor sit amet."},
                {id: 2, title: "Hello, another world", body: "consectetur adipiscing elit."},
                {id: 3, title: "Hello, final world", body: "sed do eiusmod tempor incididunt ut labore et dolore magna aliqua."},
            ],
            dialogVisible: false,
        }
    },
    methods: {
        createPost(post){
            console.log(post)
            this.posts.push(post);
            this.dialogVisible = false;
        },
        removePost(post){
            this.posts = this.posts.filter(p => p.id !== post.id) 
        },
        showDialog(){
            this.dialogVisible = true
        }
    },
}
</script>

<style>
    *{
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }
    .app{
        padding: 20px;
    }
</style>