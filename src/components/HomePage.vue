<script>
import Header from './Header.vue';
import Footer from './Footer.vue';
export default {
    name: 'HomePage',
    components: {
        Header,
        Footer
    },
    mounted() {
        let user = localStorage.getItem('user-info');
        if (!user) {
            this.$router.push({ name: 'Login' });
        }
    },
}
</script>

<template>
    <Header />
    <div class="view">
        <div class="col-sm-6 col-lg-4">
            <div class="book">
                <a href="#">
                    <img class="cay-cam" src="../assets/cay-cam-ngot.jpg" alt="Cây cam ngọt">
                </a>
                <div class="book-body">
                    <a href="#">
                        <h5 class="book-title">Cây cam ngọt</h5>
                    </a>
                </div>
            </div>
        </div>

        <div class="col-sm-6 col-lg-4">
            <div class="book">
                <a href="#">
                    <img class="life" src="../assets/life.jpg" alt="Life">
                </a>
                <div class="book-body">
                    <a href="#">
                        <h5 class="book-title">Life</h5>
                    </a>
                </div>
            </div>
        </div>

        <div class="col-sm-6 col-lg-4">
            <div class="book">
                <a href="#">
                    <img class="life" src="../assets/nguoi-thay.jpg" alt="Người thầy">
                </a>
                <div class="book-body">
                    <a href="#">
                        <h5 class="book-title">Người thầy</h5>
                    </a>
                </div>
            </div>
        </div>
    </div>

    <Footer />
</template>

<style>
.book a img {
    width: 320px;
    height: 400px;
}

.book a {
    text-decoration: none;
}

h5 {
    font-size: 20px;
    color: black;
}

h5:hover {
    color: blue;
}

Footer {
    position: sticky;
}
</style>
