<script setup>
import { defineProps } from "vue";

const props = defineProps({
  bookNumber: Number,
  bookHeader: String,
  bookCover: String,
  bookTitle: String,
  bookDescription: String,
  bookThemes: String,
  isDownloadActive: Boolean,
  isBookmarkActive: Boolean
});
</script>

<template>
    <div class="d-flex justify-content-center align-items-center">
        <div class="card border border-3 border-light book-card">
            <h1 :class="['position-absolute', 'px-3', 'bg-white', 'border', 'border-light', 'book-number', { 'number-blue': bookNumber === 1, 'number-green': bookNumber === 2, 'number-orange': bookNumber === 3 }]">
                {{ bookHeader }}
            </h1>
            <img class="card-img book-image" 
                :src="bookCover" />
            <div class="card-body py-1 px-2">
                <div class="d-flex justify-content-end">
                    <i :class="['bi', { 'bi-bookmark': !isBookmarkActive, 'bi-bookmark-fill': isBookmarkActive }, 'book-bookmark', { 'book-bookmark-active': isBookmarkActive }]"></i>
                </div>
                <h5 class="card-subtitle mb-1">{{ bookTitle }}</h5>
                <p class="card-text book-text">{{ bookDescription }}</p>
                <div class="d-flex justify-content-between align-items-center mb-2">
                    <div class="d-flex align-items-center">
                        <i class="bi bi-list-ol book-list me-1"></i>
                        <p class="text-muted mb-0 book-themes">{{ bookThemes }}</p>
                    </div>
                    <i :class="['bi', 'bi-download', 'book-download', { 'book-download-active': isDownloadActive }]"></i>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
.book-card {
    width: 275px;
    -webkit-box-shadow: 5px 6px 9px 0px rgba(194,194,194,1);
    -moz-box-shadow: 5px 6px 9px 0px rgba(194,194,194,1);
    box-shadow: 5px 6px 9px 0px rgba(194,194,194,1);
}

.book-number {
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

.book-bookmark-active {
    color: #dFcd4c;
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

.book-download-active {
    color: var(--primary-color);
}

.number-blue {
  color: #31A6DA;
}

.number-green {
  color: #8FC047;
}

.number-orange {
  color: #E18E28; 
}
</style>