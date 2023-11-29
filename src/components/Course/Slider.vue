<script setup>
import { defineProps } from "vue";
import Book from "../Course/Book.vue";
</script>

<template>
    <div id="carousel-1" class="carousel slide" data-bs-ride="false">
    <div class="carousel-inner">
        <div class="carousel-item active">
            <div class="container-fluid slider-background">
                <div class="row py-3">
                    <div class="col p-3">
                        <Book/>
                    </div>
                    <div class="col p-3">
                        <Book/>
                    </div>
                    <div class="col p-3">
                        <Book/>
                    </div>
                    <div class="col p-3">
                        <Book/>
                    </div>
                </div>
            </div>
        </div>
    </div>
    <div><a class="carousel-control-prev" href="#carousel-1" role="button" data-bs-slide="prev"><span class="carousel-control-prev-icon" aria-hidden="true"></span><span class="visually-hidden">Previous</span></a><a class="carousel-control-next" href="#carousel-1" role="button" data-bs-slide="next"><span class="carousel-control-next-icon" aria-hidden="true"></span><span class="visually-hidden">Next</span></a></div>
</div>
</template>

<style scoped>
.slider-background {
    background-color: var(--gray-color);
}
</style>
