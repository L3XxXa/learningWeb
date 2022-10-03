<!--Ya Ded inside-->
<template>
    <div class = "app">
        <post-form @createPostEvent="createPost"/>
        <post-list v-bind:posts="posts"/>
    </div>
</template>

<script>
    import PostForm from "@/components/PostForm.vue";
    import PostList from "@/components/PostList.vue";

    export default{
        components: {
        PostForm,
        PostList,
        PostForm
    },
    data(){
        return{
            posts:[
                {id: 1, title: "Hello, world", body: "Lorem ipsum dolor sit amet."},
                {id: 2, title: "Hello, another world", body: "consectetur adipiscing elit."},
                {id: 3, title: "Hello, final world", body: "sed do eiusmod tempor incididunt ut labore et dolore magna aliqua."},
            ],
        }
    },
    methods: {
        createPost(post){
            console.log(post)
            this.posts.push(post);
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