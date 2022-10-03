<template>
    <div class = "app">
        <div>
            <h4>
                Make new post
            </h4>
            <form @submit.prevent>
                <input
                 type="text"
                 v-bind:value="title"
                 @input="title = $event.target.value"
                 class="input" 
                 placeholder="Post name">

                <input class="input"
                @input="body = $event.target.value" 
                v-bind:value="body" 
                type = "text" 
                placeholder="Body">
            </form>
            <button class="button" @click = "createPost">Post!!!</button>
        </div>
        <div class = "empty"></div>
        <div class="post" v-for="post in posts">
            <div><strong>{{post.title}}</strong></div>
            <div><strong>Body:</strong> {{post.body}}</div>
        </div>
    </div>
</template>

<script>
export default{
    data(){
        return{
            posts:[
                {id: 1, title: "Hello, world", body: "Lorem ipsum dolor sit amet."},
                {id: 2, title: "Hello, another world", body: "consectetur adipiscing elit."},
                {id: 3, title: "Hello, final world", body: "sed do eiusmod tempor incididunt ut labore et dolore magna aliqua."},
            ],
            title: '',
            body: ''
        }
    },
    methods: {
        createPost(){
            const newPost = {
                id: Date.now(),
                title: this.title,
                body: this.body
            }
            this.posts.push(newPost);
            this.title = '';
            this.body = '';
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

    h4{
        font-size: 40px;
    }
    .empty{
        margin-top: 60px;
    }

    form{
        display: flex;
        flex-direction: column;
    }

    .button{
        margin-top: 15px;
        font-size: 20px;
        padding: 10px 20px;
    }

    .input{
        padding: 15px;
        border: 3px solid palevioletred;
        margin-top: 10px;
        font-size: 20px;
        width: 100%;
    }

    .post{
        padding: 15px;
        border: 4px solid palevioletred;
        margin-top: 10px;
        font-size: 20px;
    }
</style>