<template>
    <div v-show="posts.length>0">
        <h4 style = "margin-top: 15px">List of posts</h4>
        <post-item 
        v-for="post in posts" 
        :post="post"
        :key="post.id"
        @remove="$emit('remove', post)"
        />        
    </div>
    <h2 v-show="posts.length === 0" style="margin-top: 15px;">No posts</h2>
</template>

<script>
    import PostItem from "@/components/PostItem.vue"
    export default{
        components:{PostItem},
        props:{
            posts:{
                type: Array,
                required: true
            }
        }
    }
</script>

<style scoped>
    h4{
        font-size: 40px;
    }
</style>