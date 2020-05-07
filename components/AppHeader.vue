<template>
    <header class="header">
        <h1 class="title">Dad Jocks</h1>
        <ul>
            <li>
                <nuxt-link to="/">Home</nuxt-link>
            </li>
            <li>
                <nuxt-link to="/jokes">Jokes</nuxt-link>
            </li>
            <li>
                <nuxt-link to="/about">About</nuxt-link>
            </li>
        </ul>
    </header>
</template>

<script>
    export default {
        name: 'AppHeader'
    }
</script>

<style>
    header.header {
        text-align: center;
        background: #2b0404;
        padding: 12px;
        margin-bottom: 16px;
    }

    header.header h1 {
        color: #fff;
        padding: 8px;
        text-transform: uppercase;
    }

    header.header ul {
        list-style: none;
        margin: 0;
        padding: 0;
    }

    header.header ul li {
        display: inline-block;
    }

    header.header ul li a {
        color: #e6e148;
        font-size: 22px;
        padding: 2px;
    }

</style>