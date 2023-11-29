<script setup>
import { defineProps, ref } from "vue";

const props = defineProps({
  userFirstName: String,
  userPicture: String,
});
</script>

<template>
    <div class="d-flex px-3 py-1 rounded-pill header-dropdown">
        <span class="header-font">Hi, {{ userFirstName }}</span>
        <div class="px-3">
            <i class="bi bi-clock px-1 header-icon"></i>
            <i class="bi bi-bell px-1 header-icon"></i>
        </div>
        <div class="d-flex justify-content-center header-img">
          <img :src="userPicture"/>
        </div>
    </div>
</template>

<style scoped>
.header-dropdown {
    background-color: #5fa6d3;
}

.header-font {
    font-size: 1rem;
    color: var(--white-color);
}

.header-img {
    height: 24px;
    width: 24px;
    border-radius: 50%;
    overflow: hidden;
}

.header-icon {
    font-size: 1rem;
    color: var(--white-color);
}
</style>