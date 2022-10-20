<!--Ya Ded inside-->
<template>
    <div class = "app">
        <my-button @click="showDialog">
            Create post!!!
        </my-button >
        <my-button style="margin-left: 15px" @click="fetchPosts">
            Получить посты с jsonplaceholder
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
    import axios from "axios";

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
        },
        async fetchPosts(){
            try{
                const response = await axios.get("https://jsonplaceholder.typicode.com/posts?_limit=10");
                this.posts = response.data;
            } catch(e){
                alert(e.body)
            }
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