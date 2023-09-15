<script>
export default {
    name: 'Header',
    methods: {
        logOut() {
            localStorage.clear();
            this.$router.push({ name: 'Login' })
        }
    }
}
</script>

<template>
    <div class="nav">
        <a href="/">Home</a>
        <input type="text" placeholder="Type here">
        <button>Search</button>
        <a v-on:click="logOut" href="#">Log out</a>
    </div>
</template>

<style>
.nav {
    overflow: hidden;
    display: flex;
    align-items: center;
    background-color: #000000;
}

.nav a {
    float: left;
    color: #ebebeb;
    padding: 20px 25px;
    text-align: center;
    font-size: 20px;
    text-decoration: none;
    display: block;
    font-family: Arial, Helvetica, sans-serif;
    text-align: inherit;
}

.nav a:hover {
    background: #ddd;
    color: #333;
}

.nav button {
    color: #ebebeb;
    background-color: black;
    font-size: 20px;
    cursor: pointer;
    border: 1px solid transparent;
    width: inherit;
    height: max-content;
    padding: 20px 25px;
    position: relative;
}

.nav button:hover {
    background-color: #ddd;
}

.nav input {
    width: 300px;
    height: 50px;
}
</style>
