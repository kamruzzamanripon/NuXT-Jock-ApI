<template>
    <div class="about">
        <h1>About Jock Page</h1>
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Animi aperiam autem cum iusto praesentium quas ratione tempore tenetur. Aperiam dolorem eveniet, in molestias repudiandae sapiente?</p>
        <img src="http://lorempixel.com/output/people-q-c-705-705-8.jpg" alt="">
    </div>
</template>

<script>
    export default {
        head(){
            return {
                title: "Abou the App",
                meta:[
                    {
                        hid:'description',
                        name:'description',
                        content:'Best place for corny dad jokes'
                    }
                ]
            }
        }
    }
</script>

<style>
    .about h1 {
        text-align: center;
        margin-bottom: 18px;
    }

    .about p {
        margin-bottom: 30px;
        text-align: justify;
    }

    .about {
        text-align: center;
    }
</style>