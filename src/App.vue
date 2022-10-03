<template>
    <div>
        Это дерьмо поднялось
    </div>
    <div>
        <button @click="addLike">
            <strong>LIKE!!1!!!11</strong>
        </button>
    </div>
    <div><strong>Количество лайков {{ likes }}</strong></div>
</template>

<script>
export default{
    data(){
        return{
            likes: 0,
        }
    },
    methods: {
        addLike(){
            this.likes += 1
        }
    },
}
</script>

<style>

</style>