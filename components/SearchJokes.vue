<template>
    <div class="searchbox">
        <form @submit.prevent="xOnSubmit">
            <input type="text" v-model="text" placeholder="Search Jokes..." >
            <input type="submit" value="Search Jokes">
        </form>
    </div>
</template>

<script>
    export default {
        name: 'SearchJokes',
        data(){
            return {
                text:""
            }
        },
        methods:{
            xOnSubmit(){
                this.$emit('search-text', this.text);
                this.text = "";
            }
        }
    }
</script>

<style>
    .jokesall a {
        background: #422856;
        display: block;
        color: #fff;
        font-size: 18px;
        padding: 15px;
        margin-bottom: 8px;
        border-radius: 22px;
    }

    .jokesall {
        margin-top: 22px;
    }

    .searchbox {margin-bottom: 40px;background: #682059;padding: 16px;}

    .searchbox input[type="submit"] {
        background: #672059;
        color: #fff;
        font-weight: 600;
        border: 2px solid #c3cf11;
    }
</style>