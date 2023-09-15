<script>
import axios from 'axios';
import Footer from './Footer.vue';
export default {
    name: 'Login',
    data() {
        return {
            email: '',
            password: '',
        }
    },

    components: {
        Footer
    },

    methods: {
        async login() {
            let result = await axios.get(`http://localhost:3000/user?email=${this.email}&password=${this.password}`)

            if (result.status == 200 && result.data.length > 0) {
                localStorage.setItem("user-info", JSON.stringify(result.data))
                this.$router.push({ name: 'HomePage' })
            } else {
                alert("Incorrect email or password!")

            }
        }
    }
}
</script>

<template>
    <div class="login">
        <h1>Login</h1>
        <input type="text" v-model="email" placeholder="Enter Email">
        <input type="password" v-model="password" placeholder="Enter Password">
        <button v-on:click="login">Login</button>
        <p>Don't have account? <a href="/sign-up">Sign Up</a></p>
    </div>

    <Footer />
</template>

<style>
.login input {
    display: block;
    border: 1.5px solid;
    margin-bottom: 20px;
    margin-left: auto;
    margin-right: auto;
    width: 250px;
    height: 50px;
    opacity: 50%;
}

.login button {
    background-color: #87ceeb;
    margin-bottom: 20px;
    margin-left: auto;
    margin-right: auto;
    width: 250px;
    height: 50px;
    border: 1px solid skyblue;
}

.login h1 {
    margin-bottom: 30px;
    text-align: center;

}

.login p {
    margin-bottom: 30px;
    text-align: center;
    opacity: 60%;
}

.login button:hover {
    background-color: #99d6ee;
}

.login a {
    color: red;
    font-weight: 600;
    font-style: bold;
}

.login {
    background-color: rgb(240, 238, 220);
    padding: 0 30px;
}

Footer {
    position: absolute;
}
</style>