<template>
    <div class="jock-single">
        <nuxt-link to="/jokes">Back To Jokes</nuxt-link>
        <h2>{{ joke }}</h2>
        <hr>
        <small>Joke ID: {{ $route.params.id }}</small>
    </div>
</template>

<script>
    import axios from 'axios'

    export default {
        data(){
            return {
                joke:{}
            }
        },
        async created(){
            const config = {
                headers: {
                    'Accept' : 'application/json'
                }
            }

            try{
                const res = await axios.get(`https://icanhazdadjoke.com/j/${this.$route.params.id}`, config)
                //console.log(res.data)
                this.joke = res.data.joke;
            } catch (err) {
                console.log(err)
            }
        },
        head(){
            return {
                title: this.joke,
                meta:[
                    {
                        hid:'description',
                        name:'description',
                        content:'Best place for corny dad jokes'
                    }
                ]
            }
        },
    }
</script>

<style>
    .jock-single a {
        display: inline-block;
        background: #15425c;
        color: #fff;
        padding: 12px;
        font-weight: 700;
        margin-bottom: 25px;
    }

    .jock-single h2 {
        background: radial-gradient(#ffc56e, transparent);
        padding: 20px;
    }
</style>