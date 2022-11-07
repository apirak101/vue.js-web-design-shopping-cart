<template>
    <div class="container reveal" id="recommend">
        <div class="row">
            <div class="card" style="width: 18rem;text-align: center;">
                <div class="card-body">
                    <i class='bx bx-check-circle'></i>
                    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the
                        card's content.</p>
                    <a href="#" class="card-link">Card link</a>
                    <a href="#" class="card-link">Another link</a>
                </div>
            </div>
            <div class="card" style="width: 18rem;text-align: center;">
                <div class="card-body">
                    <i class='bx bx-bell'></i>
                    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the
                        card's content.</p>
                    <a href="#" class="card-link">Card link</a>
                    <a href="#" class="card-link">Another link</a>
                </div>
            </div>
            <div class="card" style="width: 18rem;text-align: center;">
                <div class="card-body">
                    <i class='bx bxs-shield-plus'></i>
                    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the
                        card's content.</p>
                    <a href="#" class="card-link">Card link</a>
                    <a href="#" class="card-link">Another link</a>
                </div>
            </div>
        </div>
    </div>

</template>

<script>


export default {
    name: "Recommend",
    
};
</script>

<style scoped>
.container {
    margin-bottom: 5rem;
}

.row {
    justify-content: center;
}

.card {
    margin: 20px;
}

.bxs-shield-plus,
.bx-bell,
.bx-check-circle {
    font-size: 4.5rem;

}
</style>