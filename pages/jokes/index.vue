<template>

    <div class="jokesall">
        <SearchJokes v-on:search-text="searchText"/>
        <Joke v-for="joke in jokes" :key="joke.id" :id="joke.id" :joke="joke.joke" />
    </div>
</template>

<script>
    import axios from 'axios'
    import Joke from '../../components/joke'
    import SearchJokes from '../../components/SearchJokes'
   export default {
        components:{
          Joke,
          SearchJokes
        },
       head(){
           return {
               title: "Jokes",
               meta:[
                   {
                       hid:'description',
                       name:'description',
                       content:'Best place for corny dad jokes'
                   }
               ]
           }
       },

       data(){
           return {
               jokes:[]
           }
       },

       async created(){
         const config = {
             headers: {
                 'Accept' : 'application/json'
             }
         }

         try{
             const res = await axios.get('https://icanhazdadjoke.com/search', config)
             //console.log(res.data)
             this.jokes = res.data.results;
         } catch (err) {
            console.log(err)
         }
       },
       methods:{
            async searchText(text){
                const config = {
                    headers: {
                        'Accept' : 'application/json'
                    }
                }

                try{
                    const res = await axios.get(`https://icanhazdadjoke.com/search?term=${text}`, config)
                    //console.log(res.data)
                    this.jokes = res.data.results;
                } catch (err) {
                    console.log(err)
                }
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
</style>