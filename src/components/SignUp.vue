<script>
import axios from 'axios'
import Footer from './Footer.vue'
export default {
    name: 'SignUp',
    data() {
        return {
            name: '',
            email: '',
            password: '',
        }
    },

    components: {
        Footer
    },

    methods: {
        async signUp() {
            let result = await axios.post(`http://localhost:3000/user`, {
                name: this.name,
                email: this.email,
                password: this.password
            })


            if (result.status == 201) {
                localStorage.setItem("user-info", JSON.stringify(result.data))
                this.$router.push({ name: 'Login' });
                alert('Sign up successfully!')
            }

        }
    },

    mounted() {
        let user = localStorage.getItem('user-info');
        if (user) {
            //this.$router.push({ name: 'HomePage' });
        }
    }


}
</script>

<template>
    <div class="register">
        <h1>Sign Up</h1>
        <input type="text" v-model="name" placeholder="Enter Name">
        <input type="text" v-model="email" placeholder="Enter Email">
        <input type="password" v-model="password" placeholder="Enter Password">
        <button v-on:click="signUp">Sign Up</button>
        <p>Have account? <a href="/login">Login</a></p>
    </div>

    <Footer />
</template>

<style>
.register input {
    display: block;
    border: 1.5px solid;
    margin-bottom: 20px;
    margin-left: auto;
    margin-right: auto;
    width: 250px;
    height: 50px;
    opacity: 50%;
}

.register button {
    background-color: #87ceeb;
    margin-bottom: 20px;
    margin-left: auto;
    margin-right: auto;
    width: 250px;
    height: 50px;
    border: 1px solid skyblue;
}

.register h1 {
    margin-bottom: 30px;
    text-align: center;

}

.register p {
    margin-bottom: 30px;
    text-align: center;
    opacity: 60%;
}

.register button:hover {
    background-color: #99d6ee;
}

.register a {
    color: red;
    font-weight: 600;
    font-style: bold;
}

.register {
    background-color: rgb(240, 238, 220);
    padding: 0 30px;
}

Footer {
    position: absolute;
}
</style>

