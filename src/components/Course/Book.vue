<script setup>

</script>

<template>
    <div class="d-flex justify-content-center align-items-center">
        <div class="card book-card border border-3 border-light" style="width: 275px;">
            <h1 class="position-absolute px-3 bg-white border border-light book-number">1°</h1>
            <img class="card-img book-image" 
                src="https://patimes.org/wp-content/uploads/2022/12/History-alternative-image-for-PA-Times.jpg" />
            <div class="card-body py-1 px-2">
                <div class="d-flex justify-content-end">
                    <i class="bi bi-bookmark book-bookmark"></i>
                </div>
                <h5 class="card-subtitle mb-1">Nombre Libro</h5>
                <p class="card-text book-text">Nullam id dolor id nibh ultricies vehicula ut id elit.</p>
                <div class="d-flex justify-content-between align-items-center mb-2">
                    <div class="d-flex align-items-center">
                        <i class="bi bi-list-ol book-list me-1"></i>
                        <p class="text-muted mb-0 book-themes">20 temas</p>
                    </div>
                    <i class="bi bi-download book-download"></i>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
.book-card{
    -webkit-box-shadow: 5px 6px 9px 0px rgba(194,194,194,1);
    -moz-box-shadow: 5px 6px 9px 0px rgba(194,194,194,1);
    box-shadow: 5px 6px 9px 0px rgba(194,194,194,1);
}

.book-number{
    font-size: 28px;
    font-weight: 700;
    width: 48px;
    height: 48px;
    border-radius: 4px 0px 4px 0px;
    display: flex;
    justify-content: center;
    align-items: center;
    -webkit-box-shadow: 5px 6px 9px 0px rgba(0,0,0,0.41);
    -moz-box-shadow: 5px 6px 9px 0px rgba(0,0,0,0.41);
    box-shadow: 5px 6px 9px 0px rgba(0,0,0,0.41);
}

.book-image {
    height: 160px;
    object-fit: cover;
    border-radius: 4px 4px 0px 0px;
    object-position: 50 50;
}

.book-bookmark {
    font-size: 20px;
    color: gray;
}

.book-text {
    font-size: 12px;
    color: gray;
}

.book-list {
    font-size: 12px;
    color: gray;
}

.book-themes {
    font-size: 10px;
    color: gray;
}

.book-download {
    font-size: 12px;
    color: gray;
}
</style>