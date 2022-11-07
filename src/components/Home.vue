<template>
    <div class="home" id="home">
        <div class="c-home">
            <div class="text-title">
                <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. repudiandae ipsam! Tempora, architecto
                    ducimus.</p>
                <a href="#productlist" class="btn-shop">SHOP NOW</a>
            </div>
        </div>
    </div>

    
</template>

<script>


export default {
    name: "Home"
};
</script>

<style scoped>
.home {
    width: 100%;
    height: 95vh;
    background-image: url(../assets/bg-home.jpg);
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
    box-shadow: 0 1px 10px rgba(0, 0, 0, 0.3);
    margin-bottom: 5rem;

    position: relative;
}

.text-title {
    text-align: center;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    z-index: 350;
}

.text-title p {
    font-size: 16px;
    margin-bottom: 2rem;
    text-shadow: 0 1px 10px rgba(0, 0, 0, 0.2);
    color: rgb(30, 30, 30);
}

.btn-shop {
    border: none;
    font-size: 14px;
    padding: 10px 10px;
    transition: 300ms;
    background: #eeeeee;
    box-shadow: 0 1px 10px rgba(0, 0, 0, 0.3);
    text-decoration: none;
    color: #000;
    border-radius: 5px;
}

.btn-shop:hover {
    border: none;
    background: #fff;
    box-shadow: 0 1px 10px rgba(0, 0, 0, 0.6);

}
</style>